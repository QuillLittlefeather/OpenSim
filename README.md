Welcome to OpenSim!

#Custom Changes
This Branch of OpenSim Contains Extended Ossl Functions and other changes


# Overview

OpenSim is a BSD Licensed Open Source project to develop a functioning
virtual worlds server platform capable of supporting multiple clients
and servers in a heterogeneous grid structure. OpenSim is written in
C#, and can run under Mono or the Microsoft .NET runtimes.

This is considered an alpha release.  Some stuff works, a lot doesn't.
If it breaks, you get to keep *both* pieces.

# Compiling OpenSim

Please see BUILDING.md if you downloaded a source distribution and 
need to build OpenSim before running it.

# Running OpenSim on Windows

You will need .NET 4.0 installed to run OpenSimulator.

We recommend that you run OpenSim from a command prompt on Windows in order
to capture any errors.

To run OpenSim from a command prompt

 * cd to the bin/ directory where you unpacked OpenSim
 * run OpenSim.exe

Now see the "Configuring OpenSim" section

# Running OpenSim on Linux

You will need Mono >= 2.10.8.1 to run OpenSimulator.  On some Linux distributions you
may need to install additional packages.  See http://opensimulator.org/wiki/Dependencies
for more information.

To run OpenSim, from the unpacked distribution type:

 * cd bin
 * mono OpenSim.exe

Now see the "Configuring OpenSim" section

# Configuring OpenSim

When OpenSim starts for the first time, you will be prompted with a
series of questions that look something like:

	[09-17 03:54:40] DEFAULT REGION CONFIG: Simulator Name [OpenSim Test]:

For all the options except simulator name, you can safely hit enter to accept
the default if you want to connect using a client on the same machine or over
your local network.

You will then be asked "Do you wish to join an existing estate?".  If you're
starting OpenSim for the first time then answer no (which is the default) and
provide an estate name.

Shortly afterwards, you will then be asked to enter an estate owner first name,
last name, password and e-mail (which can be left blank).  Do not forget these
details, since initially only this account will be able to manage your region
in-world.  You can also use these details to perform your first login.

Once you are presented with a prompt that looks like:

	Region (My region name) #

You have successfully started OpenSim.

If you want to create another user account to login rather than the estate
account, then type "create user" on the OpenSim console and follow the prompts.

Helpful resources:
 * http://opensimulator.org/wiki/Configuration
 * http://opensimulator.org/wiki/Configuring_Regions

# Connecting to your OpenSim

By default your sim will be available for login on port 9000.  You can login by
adding -loginuri http://127.0.0.1:9000 to the command that starts Second Life
(e.g. in the Target: box of the client icon properties on Windows).  You can
also login using the network IP address of the machine running OpenSim (e.g.
http://192.168.1.2:9000)

To login, use the avatar details that you gave for your estate ownership or the
one you set up using the "create user" command.



# More Information on OpenSim

More extensive information on building, running, and configuring
OpenSim, and participate in the OpenSim
project can always be found at http://opensimulator.org.

Thanks for trying OpenSim, we hope it is a pleasant experience.

#ChangeLog
Added: osEncodeSHA256  (Threat level None)

Added: osDecodeSHA256  (Threat level None)

Added: osDerezObject   (Threat level high)
   
Added: osRandomOrg     (Threat level None)

Added: MessageUrl 

#ChangeLog How to use

string osEncodeSHA256("text to encrypt","password")

string osDecodeSHA256("encoded text","password")

integer osRandomOrg(min,max)

MessageUrl is used to generate the welcome message from a web script
If MessageUrl is enabled and set then this will override the WelcomeMessage option in the ini
Note changing the welcome message text in the ini or the webserver no longer requires you to reset 
opensim/robust as it looks it up on every login. change between MessageUrl and WelcomeMessage 
Requires restarting
	
If you add <USERNAME> anywhere anywhere in the welcome message in the ini or webserver it will replace it ;with the first and last name of the user logging in


