# LDT NodeMCU Integration

This project integrates NodeMCU support in Lua Development Tools (LDT) as a new Execution Environment.

No debugging support! Only autocomplete!

LDT can be a downloaded as a standalone IDE or as a part of Eclipse IDE.

More Infos at: https://eclipse.org/ldt/

The documentation is inherited from http://nodemcu.readthedocs.io/en/dev/en/ and https://github.com/nodemcu/nodemcu-firmware (source files).
Some parts have been removed or edited.

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

##Autocomplete support
If your project's Execution Environment is set correctly, you will get autocomplete support for NodeMCU specific functions.

![Autocomplete](/pics/autocomplete01.png?raw=true)

Note: The default Lua modules "io" and "os" are not available in NodeMCU (http://nodemcu.readthedocs.io/en/dev/en/lua-developer-faq/#how-is-nodemcu-lua-different-to-standard-lua).
I made a screenshot from ESPlorer to show which default Lua modules are available. (The romtable addresses may differ in your firmware.)

![Default Lua modules in NodeMCU](/pics/nodemcu-default-lua-modules01.png?raw=true)

##Modules implemented
The following table describes the progress of integration of the NodeMCU modules.

| Module       | Integration  |
| ------------ |:------------:|
| dht          | full         |
| file         | partly       |
| gpio         | partly       |
| i2c          | full         |
| mqtt         | no           |
| net          | partly       |
| node         | partly       |
| tmr          | partly       |
| wifi         | partly       |

You need a module that isn't already listet here?

You need a function that isn't already documented?

You found a mistake in documentation?

**Open an issue on github! Or fix it yourself and send a pull request!**


##Links
https://wiki.eclipse.org/LDT/User_Area/Tutorial/Create_a_simple_Execution_Environment

https://wiki.eclipse.org/LDT/User_Area/Execution_Environment_file_format