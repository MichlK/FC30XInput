Fork notes:

This quick fork was created for the FC30 PRO (and NES30 PRO) game controller by 8bitdo - http://8bitdo.com/fc30pro/ - to map the analogue sticks and additional buttons in Bluetooth mode. Tested with firmware 1.68 - works fine!

Installation / usage:
# Download and start DS4Windows, so that the driver for the X360bus is installed: http://ds4windows.com/
# Power the FC30 Pro game controller on in default mode (by just pushing the power button; without a USB-cable plugged in)
# Make sure the controller is paired with your computer
# Open the application, select the controller & the button layout and start the emulation
# Have fun...

BTW: I included a dirty fix - Thread.sleep(1) - so that polling the DirectInput data does not consume a CPU core... :-)

--------------------------

Original readme by ROFISH:

This is an early release of an app that converts DirectInput commands into XInput commands for the FC30 controllers.

Why would you do this? Well, many games now just use XInput instead of looking at DirectInput. And why would you blame them? It prefills known buttons and works immediately for Microsoft's controllers. As an out-of-the-box gaming experience, it's pretty great. I have one myself.

However, what you want or need to use another controller? The 360 controllers's d-pad is garbage and plenty of retro or faux-retro games work better on older controllers. I got an 8BitDo SFC30 off Amazon. It works great except that it's just a generic DirectInput controller instead of XInput. So games like Downwell don't work at all for a controller it's clearly meant for. This app fixes that problem so that it's WAY WAY more useful.

Also, I know that 360ce exists; but I wanted a way more elegant solution over having to copy DLLs everywhere and rehook into a system.

Requirements:

* Windows 7 SP1 or up has XInput preinstalled, but lower versions of Windows has XInput here: https://www.microsoft.com/hardware/en-us/d/xbox-360-controller-for-windows
* .NET 4.5.2: https://www.microsoft.com/en-us/download/details.aspx?id=42643
* Any DirectInput controller, but for now the buttons are hardcoded for the SFC30 controller I have.

Usage:

# SFC30 BT Mode: Use the START+R mode for joystick mode. USB works directly.
# Open App
# Select Controller (use refresh button to refresh list)
# Select how you want the D-Pad to be handled, use either as Xinput LS or D-Pad.
# Select how you want the face buttons to be handled (either as labeled on the SFC30, or duplicating the Xinput controller scheme instead)
# Press Start Emulation to start. It will work with the USB driver to pretend a controller was connected; should work in every game since it is effectively a real XInput controller to any other app.
# Press Stop to Stop.
# In case the app crashes and it leaves the USB emulation in a weird state, there's a force unplug button. (Not really recommended if you have a real controller plugged in too.)
# XInputText.exe is included for easy testing.

Known Limitations:

* This controller always pretends to be controller 1. No multiples allowed.

Special Thanks:

DS4Windows: https://github.com/Jays2Kings/DS4Windows . The 360 emulator part was ripped from this project and couldn't have happened without it.
