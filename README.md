# Fixing-VT-x-in-Bios
If you are missing VT-x within your bios use this to resolve your issue.


You will run the Export.bat first, if you have issues with getting information then you have to run SCEWIN_FIX then it will work.
  - When you complete the Export.bat it will make a file called "nvram"
  - within that .txt file you find what you need thats hidden within your bios, for me and most of you its "VT-x" or also known as "Intel (VMX) Virtualization Technology"

it will look like this 

Setup Question	= Intel (VMX) Virtualization Technology
Help String	= When enabled, a VMM can utilize the additional hardware capabilities provided by Vanderpool Technology.
Token	=2D5	// Do NOT change this line
Offset	=B9
Width	=01
BIOS Default	=[01]Enabled 
Options	=[00]Disabled	// Move "*" to the desired Option
         *[01]Enabled


********
What you want to do is delete the * before [01]Enabled and add it infront of [00]Disabled like this 

Setup Question	= Intel (VMX) Virtualization Technology
Help String	= When enabled, a VMM can utilize the additional hardware capabilities provided by Vanderpool Technology.
Token	=2D5	// Do NOT change this line
Offset	=B9
Width	=01
BIOS Default	=[01]Enabled 
Options	=*[00]Disabled	// Move "*" to the desired Option
         [01]Enabled

***************

After that you can do the same for any other features that you are looking for and save the .txt 

Finally run the Import.bat and restart your PC, you will now have it disabled/enabled for any features that you changed. 
