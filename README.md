# Fusion-360-Scipts

This script exports the tools, names and length offsets to Mach3 but not diameter offsets.

I use Mach3 on a CNC router. Normally all my tool offset stuff are handled by Fusion 360.
The reason i want to sync tooltables between Mach3 and Fusion 360 is because i change tools manually.

I use a custom toolchange script m6start.m1s on Mach3 which;

* Goes to a toolchange position for reaching easily
* Reads out the toolname like "6 milimeter downcut endmill" instead of a toolnumber, using the "speak" command on mach3 vbscript
* After the toolchange, user clicks the ok button to proceed with auto tool zero move to my touchoff tool
* To reduce time of the tool zeroing process, my code rapids into the touchoff stopping before 5 to 10 mm.
* Here tool length offset helps to avoid crashes or slow probing moves, because some tools are really short like engraving tools and long tools like drill bits.


# Usage

* When i add a new tool or make changes, i run the script inside fusion.
* Make sure the script points out the correct tool list which is a json file inside fusion folders
* The script generates a file (called m700.m1s in my example)
* In my mach3 settings, "m700" is included in my initialization line on the settings window, so its called
on startup and when reset button is pressed.

Make sure to change paths and filenames to your needs.
