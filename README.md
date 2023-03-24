# Maniac-Chamber-Lighting

This project uses 24V high efficiency white COB LED strip lighting to provide interior lighting on a Voron 2.4 350/300/250.

One of the goals of this project is to simplify installation of lighting with snap in mounting brackets and pre-assembled wiring and junction boxes, and eliminate the use of screws. The commonly available adhesive backed 24V COB strips are cut to size in increments of 50mm and attached to each printed LEDBar.  

Aluminized Mylar tape attached to the LEDBar forms a corner reflector to improve light output. A combination of light baffles/diffusers on the side strips along with installation angle of the front and rear LEDBars prevents glare as the COB elements themselves are not directly visible when viewed from the front of the Voron.  The lights are connected to a PWM MCU output that can be connected to a Klipper input button or Mainsail dimmer slider.  

The LEDBars are designed to just fit along the top frame rails and include a 2mm JST connectors for easy installation and removal while servicing the printer.  Printed brackets "permanently" snap into the 2020 and the LEDBars in tern snap into these brackets making for quick removal of the LEDBars as needed.

Printed zero clearance snap in 2020 slot covers make for clean installation and wire management. 
A printed TPU Z belt cover is included that of course snaps into the 2020, making the wire run from the vertical 2020 section to the electronics bay non-exposed.  A complete set of TPU parts to seal and support the base panel will be published later.

The design was prototyped on a Voron 350, but STL and STEP files are included for 300 and 250 printers.  The LEDBars must be printed at a 45 degree angle to fit on the build plate.  Double check that you can fit the LEDBar on your build plate before committing to the project and ordering parts.


![](https://github.com/VoronManiac/Maniac-Chamber-Lighting/blob/main/Image/PXL_20230319_191023708.jpg?raw=true)

![](https://github.com/VoronManiac/Maniac-Chamber-Lighting/blob/main/Image/Composite1.jpg?raw=true)

## BOM
| Qty        | Item           | Comment |
|:------------- |:------------- |:----- |
| 2m           | 24V COB strip; 50mm segments; adhesive backed | https://www.amazon.com/gp/product/B0B9SFMZ1L  |
| 1 roll  | Aluminumized Mylar Tape 1/2" (12.7mm) |  https://www.amazon.com/gp/product/B07TYKFS8K  |
| 10ft/3m      | Red 26awg PTFE stranded wire | less than $0.15/foot  ebay/Amazon/AliExpress |
| 10ft/3m      | Black 26awg PTFE stranded wire | less than $0.15/foot  ebay/Amazon/AliExpress |
| 4 | JST 2.0 4-Pin Male Connector plug with Wire + Female Connector plug(have not cable) |   https://www.amazon.com/gp/product/B01DUC1S7S |
| - | solder | |
| - | CA glue & accelerator | |


## Printer Tuning
Print STL/Tools/Test.stl.  

Measure the width of the 5mm arms at the two points indicated and verify they are within 0.05mm.  Measure the length of the arms to be 100mm to be within 0.10mm.  Check for no elephant foot.  If every looks good, print the STL/Common/LEDBar50.stl.   Insert a Female JST plug and test fit the STL/Common/LEDEnd.stl.  Otherwise follow the tuning suggestions below

![](https://github.com/VoronManiac/Maniac-Chamber-Lighting/blob/main/Image/TestPrint.jpg?raw=true)

### Test print width and length adjustment

The width of the 5mm section of the test print is primarily influenced by the slicer's filament extrusion multiplier.  To dial it in, do two test prints with different extrusion multipliers and linearly interpolate between the two to determine the correct setting.  

The 100mm length is primarliy influenced by the filament shrinkage factor.  Again, do two prints and linearly interpolate.

There is some interaction between the two settings so it may require some iteration.

### Test print varying 5mm thickness

If the two 5mm width measurements differ, and assuming Pressure Advance is dialed in, chances are the difference is caused by temperature flow variation.

In the same way Pressure Advance has to build up pressure at the beginning of a new extrusion to control print width, there is a secondary factor that the extrusion pressure builds slightly on long high flow rate lines because the extrusion temperature of the melt decreases. At high flow rates, the filament has less time to reach full temperature compared to printing slowly.  This effect is very pronounced with TPU but also observed with ABS.  The net effect is over extrusion once the flow rate decreases as in the case of a 90 degree turn.  Pressure advance does attempt to decrease pressure when decelerating but it does not take into account the pressure increase due the tempeature drop and the increased flow as the temperature returns to a normal level with the flow decreases...  bottom line try decreasing the peak flow rate/print speed to minimize the effect. 





## Assembly
### LED Bar
### Junction Boxes
### Installation
