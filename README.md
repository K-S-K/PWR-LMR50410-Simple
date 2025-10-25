# PWR-LMR50410-Simple

Simple LMR50410 DC-DC Converter

## External documents
[Design rules for JLCPCB](https://forum.kicad.info/t/design-rules-for-jlcpcb/46087)

[Mastering PCB Design Rules: A Comprehensive Guide for Optimal Results](https://jlcpcb.com/blog/a-comprehensive-guide-for-optimal-results)

[PCB Manufacturing & Assembly Capabilities](https://jlcpcb.com/capabilities/pcb-capabilities)

[Simulation examples for KiCad8/KiCad9/Eeschema/ngspice](https://forum.kicad.info/t/simulation-examples-for-kicad8-kicad9-eeschema-ngspice/45546)

## How to uninstall KiCad from macOS

If you install KiCad ‘conventionally’, it gets installed to the following folders.

1. The KiCad folder in "**/Applications**". This contains the main applications.

2. The “kicad” folder is in "**/Library/Application Support**", which contains the assets (footprints/libraries/models/templates), etc.

3. The KiCad preferences in "**~/Library/Preferences/kicad**". Most importantly, these include fp-lib-table and sym-lib-table, as well as various preference files. For 5.99, the preferences are stored separately within a ‘5.99’ directory. You need to remove all the files in this directory to remove all the settings.

This is the standard ‘default’ installation. If you simply remove (3) the next time you run KiCad, it will run the ‘first install’ wizard and regenerate default preferences.

It is, of course, possible to set things up differently and use environmental variables to point to resources in different locations, symlink files to shared locations, and perform multiple other tricks. You can place libraries wherever you like so you need to check the entries in the "**Kicad -> Preferences -> Configure paths ...**" menu to check that there are not any assets that you have relocated that you want to remove.

You will also notice that it is possible to keep a 5.1.x installation and a 5.99 installation separate with different preferences, and you need to remove the 5.99 folder if you want to reset this as well.

When you reinstall KiCad, if there is a pre-existing ‘kicad’ folder in "**~/Library/Preferences**", you KEEP your original preferences. This is the only directory you need to remove to reset to ‘factory fresh’. This is a common paradigm on macOS - if you have futzed up an applications setting and can’t seem to reset it or it doesn’t start, deleting the preferences is a good way of resting the app back to its ‘out of the box’ settings.

---

In addition and for completeness, the "**~/Library/Preferences/kicad/**" folder contains a scripting folder. This is used for plugins, and you might want to preserve the contents between installs to keep any plugins. On a practical point, it is probably easiest for maintenance to symlink the original files into the scripting directory.

There are plans for the forthcoming v6 to have a plugin manager. At present, the scripts are in "**~/Library/Preferences/kicad/5.99/scripting**".

The following directories are also searched for plugins, which are where the stock footprint wizards live.

"**/Applications/KiCad/KiCad.app/Contents/SharedSupport/scripting**"
"**/Applications/KiCad/KiCad.app/Contents/SharedSupport/scripting/plugins**"

(Based on [the KiCad forum message](https://forum.kicad.info/t/mac-os-how-to-remove-it-all/31264/2)).
