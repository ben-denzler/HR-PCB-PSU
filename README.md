# PCB Power Supply

 Author: [Benjamin Denzler](https://github.com/ben-denzler)
 
 ## Project Description

This is a project I did as a member of Highlander Racing, UCR's FSAE club. I created schematics and PCB layouts for a power supply that can take a 12V input and convert it to 5V and 3.3V outputs to power components on a board. After designing the power supply, I implemented it on one of the boards for the club's car: the Sensor Telemetry Module (STM)!

The power supply consists of two parts: an [LTC3646 step-down converter](https://www.analog.com/en/products/ltc3646.html#product-overview) that takes a 12V input from the car's battery and steps it down to 5V, and an [NCV1117 linear voltage regulator](https://www.onsemi.com/products/power-management/linear-regulators-ldo/ncv1117) that takes 5V as input and converts it to a 3.3V output.

## LTC3646 step-down converter

The LTC3646 was chosen to convert 12V from the car's battery to a 5V output because of its efficiency. The boards used in our vehicle are enclosed in small boxes, so a switching regulator was needed to reduce heat output during this conversion. This component is AEC−Q100 qualified, so it is appropriate for automotive applications.

### Design considerations

* The suggested PCB layout given by the LTC3646's datasheet was used as a starting point, with modifications made to match our board's components.
* Space was left in between the IC and the inductor to minimize the inductor's interference with the IC.
* Vias were placed below the LTC3646 IC to help dissipate heat into the board's copper.
* PCB layout and schematic were annotated to help other team members understand their design.

### Images

LTC3646 schematic document:

![LTC3646 Schematics](images/LTC3646_Schematic.png)
 
LTC3646 PCB layout (2D view):

![LTC3646 2D view](images/LTC3646_2D.png)
 
LTC3646 PCB layout (3D view):

![LTC3646 3D view](images/LTC3646_3D.png)

## NCV1117 linear voltage regulator

Since a switching regulator was used to efficiently convert 12V to 5V, we chose the NCV1117, a linear voltage regulator, to convert the 5V input to a 3.3V output. The smaller voltage difference creates less heat and the simplicity of linear regulators saves on both space and cost. Additionally, the NCV1117 is also AEC-Q100 qualified, so it is suited for automotive applications.

### Design considerations

* Layout was made to easily connect to the output of our LTC3646 switching regulator.
* Design size was minimized to save space on our small boards.
* Vias were placed under the IC to help with heat dissipation into the board's copper.
* Copper pour for the IC is easily adjustable to fit different board shapes while still cooling sufficiently.

### Images

NCV1117 schematic document:

![NCV1117 Schematics](images/NCV1117_Schematic.png)
 
NCV1117 PCB layout (2D view):

![NCV1117 2D view](images/NCV1117_2D.png)
 
NCV1117 PCB layout (3D view):

![NCV1117 3D view](images/NCV1117_3D.png)
 
 ## Application
 
 This power supply was used to deliver power to a board called the Sensor and Telemetry Module and is pictured below in the board's upper left corner. I added the power supplt to the board and did layout for its traces. My design was slightly modified to fit better on this board and to improve cooling for the linear regulator. It takes 12V input from the battery, then delivers 5V to components like AND gates, comparators and transcievers, while delivering 3.3V to the board's microcontroller and SD card reader.
 
STM board (2D view):

![STM 2D view](images/STM_2D.png)

STM board (3D view):

![STM 3D view](images/STM_3D.png)
