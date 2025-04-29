# BASTL Laser Tool

Inkscape extension to generate laser cutter g-code comptible with 3D printer firmwares. In the first place oriented to Repetier firmware.

**Compatibility note:** This tool is compatible with Inkscape version 0.95. It cannot be used with Inkscape version 1.0 and newer.


It is based on [**JFU Laser tool**](http://www.fucik.name/hw/laser/jfu_laser.php) and [**J Tech Photonics Laser Tool**](https://jtechphotonics.com/?page_id=2012).

Features:

* supports Repetier firmware *Laser Mode*
* laser intensity is taken from "transparency" attribute of path (transparency attribute of compounds and groups are ignored)
* differentiates `G1` (cutting) and `G0` (move) commands (in original extensions all moves and cuts were implemented as `G1` command)
* speed modulation of laser intensity
* acceleration control for low speed moves
* support for external PWM generator
* software focusing (setting of Z level)
* X and Y offset

Following options are available:

- **Laser Mode:**  flavour of generated g-code: compatible with Repetier Laser Mode or GRBL
- **Laser ON Command:**  Command to turn laser on in GRBL mode, setting of laser intensity in Repetier mode. Typically `M03`.
- **Laser OFF Command:** Command to turn laser off (typically `M05`). Used in GRBL mode only.
- **Laser Intensity Command:** Code to control external PWM module. When defined, *"Laser ON"* command always uses maximum laser power.
- **Use speed to Control Intensity:** Laser intensity is controlled by move speed. When enabled, *"Laser ON"* command always uses maximum laser power.
- **Additional initialization:** additional initialization code; m ultiple commands can be separated by "|" (vertical bar character)
- **Initial Z-level:** Initial (zero) level; at this level laser should be focused on material surface
- **X-offset:** X offset
- **Y-offset:** X offset
- **Travel Speed:**  Nominal speed during moves (laser off)
- **Laser Speed:**   Nominal speed during cuts (laser on). Speed can vary if speed modulation is enabled
- **Laser Power:** value for maximum laser intensity. It can be reduced depending on path transparency. Repetier firmware uses value 255, GRBL uses value 12000.
- **Power On Delay:** Delay after turning laser on; used in GRBL mode only, Repetier firmware uses built-in value
- **Passes:**  Number of passes necessary to cut material thoroughly
- **Pass Depth:** Penetration depth during single pass. The head is lowered by this value between passes
- **Directory:**  directory where created files are placed
- **Filename:**  name of output file.
- **Add numeric suffix to filename:** When enabled, sequentce number is attached to filename
- **Units:**  Units used in output file (mm or inch)
- **Live preview:**  Live changes on screen, when parameters are changed.
- **Enable acceleration control** - enables acceleration control for low speed moves
- **Printer X/Y steps per mm:** - number of steps per mm of stepper motor (both X and Y axes)
- **Printer X/Y acceleration:** - maximum acceleration (both X and Y axes)

