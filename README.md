# LDT NodeMCU Integration

This project integrates NodeMCU support in Lua Development Tools (LDT) as a new Execution Environment.

**No debugging support! Only autocompletion!**

LDT can be a downloaded as a standalone IDE or as a part of Eclipse IDE.

More Infos at: https://eclipse.org/ldt/

The documentation is inherited from http://nodemcu.readthedocs.io/en/dev/en/ and https://github.com/nodemcu/nodemcu-firmware (source files).
Some parts have been removed or edited.

NodeMCU is a eLua based firmware for ESP8266 chips to run Lua programs.
You can build your custom NodeMCU firmware at http://nodemcu-build.com (or use other methods https://nodemcu.readthedocs.io/en/dev/en/build/).

##Installation
Download the zip file in the "release" directory of your desired NodeMCU Version of this repository.

Open LDT (or Eclipse) and go to Preferences. On the left side choose "Lua".

Click on "Execution Environment" and then the "Add..." button.

![Add zip](/pics/add-ee-compact01.png?raw=true)

Select the downloaded zip file. Then you should see it in the list of the Execution Environments.

If you want, you can tick the Lua NodeMCU Execution Environment to make it the default one.

Click on "OK" to close the preferences window.

Now you can click on File->New->Lua Project and select the Lua NodeMCU Execution Environment.

![Create Project](/pics/create-proj01.png?raw=true)

##Autocompletion support
If your project's Execution Environment is set correctly, you will get autocompletion support for NodeMCU specific functions.

![Autocomplete](/pics/autocomplete01.png?raw=true)

Note: The default Lua modules "io" and "os" are not available in NodeMCU (http://nodemcu.readthedocs.io/en/dev/en/lua-developer-faq/#how-is-nodemcu-lua-different-to-standard-lua).
I made a screenshot from ESPlorer to show which default Lua modules are available. (The romtable addresses may differ in your firmware.)

![Default Lua modules in NodeMCU](/pics/nodemcu-default-lua-modules01.png?raw=true)

##Modules integrated
The following table shows the progress of integration of the NodeMCU modules for LDT.
In addition you see which modules are availabe in the specific NodeMCU versions.

Note: The IDE doesn't know which modules are included in your custom NodeMCU firmware.
You will always get displayed all modules for autocompletion that are in the Execution Environment Zip!

| Module       | Integration  | NodeMCU 1.4.0 | NodeMCU 1.5.1 |
| ------------ |:------------:|:-------------:|:-------------:|
| am2320       | no           | no            | yes           |
| bit          | full         | yes           | yes           |
| dht          | full         | yes           | yes           |
| file         | partly       | yes           | yes           |
| gpio         | full         | yes           | yes           |
| http         | no           | no            | yes           |
| i2c          | full         | yes           | yes           |
| mqtt         | no           | yes           | yes           |
| net          | partly       | yes           | yes           |
| node         | partly       | yes           | yes           |
| ow           | no           | yes           | yes           |
| tmr          | full         | yes           | yes           |
| wifi         | partly       | yes           | yes           |

* You need a module that isn't already listed here?

* You need a function that isn't already integrated?

* You found a mistake in this project?

**Open an issue on github! Or fix it yourself and send a pull request!**


##Links
https://wiki.eclipse.org/LDT/User_Area/Tutorial/Create_a_simple_Execution_Environment

https://wiki.eclipse.org/LDT/User_Area/Execution_Environment_file_format