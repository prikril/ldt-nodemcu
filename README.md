# LDT NodeMCU Integration

This project integrates NodeMCU support in Lua Development Tools (LDT) as an new Execution Environment.

As a result you will get an good NodeMCU IDE to write better code more easier.

**No debugging support! Only autocompletion (autocomplete, code completion, content assist)!**

LDT can be downloaded as an standalone IDE or as a part of Eclipse IDE.

More Infos at: https://eclipse.org/ldt/

The documentation is inherited from http://nodemcu.readthedocs.io/en/dev/en/ and https://github.com/nodemcu/nodemcu-firmware (source files).
Some parts have been removed or edited.

NodeMCU is a eLua based firmware for ESP8266 chips to run Lua programs.
You can build your custom NodeMCU firmware at http://nodemcu-build.com (or use other methods https://nodemcu.readthedocs.io/en/dev/en/build/).

##Installation
Download the zip file in the "release" directory of your desired NodeMCU Version of this repository or use the direct links:

*old (only minimal LDT integration):*

*NodeMCU 1.4.0: https://github.com/prikril/ldt-nodemcu/raw/master/lua5.1-nodemcu1.4.0/release/lua5.1-nodemcu1.4.0.zip*

**current (recommended version):**

**NodeMCU 1.5.1: https://github.com/prikril/ldt-nodemcu/raw/master/lua5.1-nodemcu1.5.1/release/lua5.1-nodemcu1.5.1.zip**


Open LDT (or Eclipse) and go to Preferences. On the left side choose "Lua".

Click on "Execution Environment" and then the "Add..." button.

![Add zip](/pics/add-ee-compact02.png?raw=true)

Select the downloaded zip file. Then you should see it in the list of the Execution Environments.

If you want, you can tick the Lua NodeMCU Execution Environment to make it the default one.

Click on "OK" to close the preferences window.

Now you can click on File->New->Lua Project and select the Lua NodeMCU Execution Environment.

![Create Project](/pics/create-proj01.png?raw=true)

##Install Updates
If you want to add a new version of the NodeMCU Execution Environment, you need to remove the current one first.

Select the execution environment in the list as described above. Click the "Remove" button.

Then add the new zip. (Same steps as above.)

##Autocompletion support
If your project's Execution Environment is set correctly, you will get autocompletion support for NodeMCU specific functions.

![Autocomplete](/pics/autocomplete01.png?raw=true)

Note: The default Lua modules "io" and "os" are not available in NodeMCU (http://nodemcu.readthedocs.io/en/dev/en/lua-developer-faq/#how-is-nodemcu-lua-different-to-standard-lua).
I made a screenshot from ESPlorer to show which default Lua modules are available. (The romtable addresses may differ in your firmware.)
Not all functions from "math" are available! Consider https://github.com/nodemcu/nodemcu-firmware/blob/master/app/lua/lmathlib.c to see which functions can be used.

![Default Lua modules in NodeMCU](/pics/nodemcu-default-lua-modules01.png?raw=true)

##Modules integrated
The following table shows the progress of integration of the NodeMCU modules for LDT.
In addition you see which modules are available in the specific NodeMCU versions as defined by the NodeMCU developers.
(Select "master" or "dev" branch at http://nodemcu-build.com/ and compare the available modules for more information.)

Note: The IDE doesn't know which modules are included in your custom NodeMCU firmware build.
You will always get displayed all modules and functions for autocompletion that are integrated in the selected Execution Environment!

The current (2016-06-03) version of NodeMCU Master branch is 1.5.1, the old version 1.4.0 is not supported by this project anymore.
The old version (1.4.0) won't get updates any longer (since 2016-06-03) by this project.

Please use the latest version from NodeMCU to get the newest modules and functions.

| Module       | Integration  | 1.4.0 (old)   | 1.5.1         | Comment                                |
| ------------ |:------------:|:-------------:|:-------------:| -------------------------------------- |
| am2320       | no           | no            | yes           |                                        |
| bit          | full         | yes           | yes           |                                        |
| dht          | full         | yes           | yes           |                                        |
| enduser_setup| full         | yes           | yes           |                                        |
| file         | full         | yes           | yes           |                                        |
| gpio         | full         | yes           | yes           |                                        |
| http         | full         | no            | yes           |                                        |
| i2c          | full         | yes           | yes           |                                        |
| mqtt         | full         | yes           | yes           | has some overloaded functions          |
| net          | full\*       | yes           | yes           | \*full, except: on and send for UDP server  |
| node         | full\*       | yes           | yes           | \*full, except: stripdebug, osprint, egc and deprecated functions |
| ow           | no           | yes           | yes           |                                        |
| tmr          | full         | yes           | yes           |                                        |
| wifi         | full\*       | yes           | yes           | \*full, except: eventmon, sleep, smart |

(Note: Some functions are not available in NodeMCU 1.4.0 but 1.5.1 e.g. `wifi.sta.getrssi()`.)

* You need a module that isn't already listed here?

* You need a function that isn't already integrated?

* You found a mistake in this project?

**Open an issue on github! Or fix it yourself and send a pull request!**


##Links
https://wiki.eclipse.org/LDT/User_Area/Tutorial/Create_a_simple_Execution_Environment

https://wiki.eclipse.org/LDT/User_Area/Execution_Environment_file_format

https://www.eclipse.org/forums/index.php/t/1065750/ (Possible to install NodeMCU in LDT)