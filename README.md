# Process Behaviour Chart (PBC) for Azure DevOps

## What is this report? 
This report provides a simple way to analyse the predictability and variability of a team. For the flow metrics of Throughput, Work In Progress and Cycle Time, a Process Behaviour Chart (PBC) is visualized.

The PBC (traditionally known as a Statistical Process Control - SPC chart) shows what type of variation is present in a teams flow. Any time you see a data point outside of the Upper Natural Process Limit (UNPL) or Lower Natural Process Limit (LNPL), these points highlight a signal that represents exceptional variation.

## Why would you use it? 
Separate that which is ‘signal’ from that which is ‘noise' in your data. Variability in terms of Throughput, Cycle Time and/or Work In Progress (WIP) is inevitable. Understanding when you have too much variability and when an intervention is needed is what is important. Use these charts to find out where you may need to focus. 

## When would you use it?
Use this at potentially every other retrospective to understand where there has been variation in your process/ways of working and potentially do some root-cause analysis as to why that may be.

### Prerequisites
* [Make sure you have the latest version of Power BI Desktop](https://aka.ms/pbiSingleInstaller)
* [Download the template](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/raw/main/Process%20Behaviour%20Chart.pbit)
* Then you're good to get started!

### Connectivity
* Open the .pbit file
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization and project name

Don't confuse the team name with the project name, a common mistake. If the URL you use is "http://dev.azure.com/Microsoft-UK/AzureDevOpsTeam/Database", then Microsoft-UK is the Organization Name, AzureDevOpsTeam is the Project name, Database is the team name.

* It should then look something like this:

Azure DevOps Services:
![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz/main/Screenshots/AzDO%20Services%20Login.png)


Azure DevOps Server:
![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz/main/Screenshots/AzDO%20Server%20Login.png)

* Hit 'Load' 
* If you are prompted for a login, you can choose:
  - 'Organizational' and enter your Organization email/password (if required) and sign in
  - 'Basic' and use a Personal Access Token (PAT) to login, entering it in the password field (user can be left as blank - make sure it has 'Read' access to Analytics)

  ![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!

![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/c281cdac-e719-4022-b267-0c4f3a50d569)

## Using the report
There are some key things to look for when visually analysing the charts, things to look for are:

- Any points outside the limits - A single point outside the calculated natural process limits indicates the presence of an exceptional cause that has a dominant effect. Unless it is something seasonal this is the key point to focus on (it’s a ‘signal’).
![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/9e622b1d-c3c1-4dda-99d9-2d2f59da0814)
- Shifts in the process - this can be when points are consistently positioned above/below the average line but then shift. This could allude to something that has changed with regards to the way of working.
- Cyclical/seasonal patterns - this can be when there are particular days or weeks when a shift in values occurs. It may not always mean that this is a ‘signal’.
- The run of ‘eight’ - Eight or more successive values all on the same side of the average may indicate the presence of an exceptional cause that has a weak but sustained effect.
![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/14197c28-fc8b-49eb-83b9-2acf13ec9bdb)
- Runs near the limits - Three out of four successive values all within the upper 25% of the region between the limits, or all within the lower 25% of the region between the limits, may indicate the presence of an exceptional cause that has a moderate but sustained effect.
  
[Source - Deming Alliance](https://demingalliance.org/resources/articles/process-behaviour-charts-an-introduction)
