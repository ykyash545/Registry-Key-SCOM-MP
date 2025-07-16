This repository contains a System Center Operations Manager (SCOM) Management Pack (MP) designed to monitor a specific registry key value on Windows servers.
 
It checks if a designated registry attribute matches a specified regular expression pattern and generates an alert if it does not.
The Management Pack provides a custom unit monitor that continuously checks the value of a specified registry attribute. 
Its primary purpose is to ensure that a critical registry setting, such as ServerLevel under SOFTWARE\CompanyX, maintains a desired value (e.g., 0). 
If the registry value deviates from the expected pattern, the monitor changes to an unhealthy state and triggers an alert, indicating a potential configuration issue.
Installation
To install this Management Pack:

Download: Obtain the xml file from this repository.

Import into SCOM:
Open the SCOM Operations Console.
Navigate to Administration > Management Packs.
Right-click on Management Packs and select Import Management Packs....
Click Add > Add from disk... and select the downloaded MP file.

Follow the on-screen prompts to complete the import process.

Usage
After importing the Management Pack, the ServerLevel Registry Monitor will automatically be enabled and will begin monitoring Windows Server Operating Systems.

By default, it monitors the ServerLevel attribute under SOFTWARE\CompanyX and expects its value to be 0.

Overriding Monitor Parameters
You can customize the monitoring behavior by creating overrides for the ServerLevel Registry Monitor. This allows you to specify different registry paths, attribute names, patterns, or frequencies for various server groups or individual servers.
To create an override:

In the SCOM Operations Console, navigate to Monitoring > Monitors.
Find the ServerLevel Registry Monitor.
Right-click on the monitor and select Overrides > Override the Monitor > For a specific object of class: Windows Server Operating System (or a group, if applicable).
Select the target object(s) or group.

Save the override.
