# PCB Power Supply

 Author: [Benjamin Denzler](https://github.com/ben-denzler)
 
 ## Project Description

This is a project I did as a member of Highlander Racing, UCR's FSAE club. I created schematics and PCB layouts for a power supply that can take a 12V input and convert it to 5V *and* 3.3V outputs to power components on a board. After designing the power supply, I implemented it on one of the boards for the club's car: the Sensor Telemetry Module (STM)!

The power supply consists of two parts: an [LTC3646 step-down converter](https://www.analog.com/en/products/ltc3646.html#product-overview) that takes a 12V input from the car's battery and steps it down to 5V, and an [NCV1117 linear voltage regulator](https://www.onsemi.com/products/power-management/linear-regulators-ldo/ncv1117) that takes 5V as input and converts it to a 3.3V output.

## LTC3646 step-down converter

The LTC3646 was chosen to convert 12V from the car's battery to a 5V output because of its efficiency. The boards used in our vehicle are enclosed in small boxes, so a switching regulator was needed to reduce heat output during this conversion. 

### Design considerations:
* The suggested PCB layout given by the LTC3646's datasheet was used as a starting point, with modifications made to match our board's components
* Space was left in between the IC and the inductor to minimize the inductor's EMI
* Vias were placed below the LTC3646 IC to help dissipate heat into the board's copper
* PCB layout and schematic were annotated to help other team members understand their design

### Images

LTC3646 schematic document:

 ![LTC3646 Schematics](images/LTC3646_Schematic.png)
 
 LTC3646 PCB layout (2D view):

 ![LTC3646 Schematics](images/LTC3646_2D.png)
 
  LTC3646 PCB layout (3D view):

 ![LTC3646 Schematics](images/LTC3646_3D.png)
