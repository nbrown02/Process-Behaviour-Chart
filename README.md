# Process Behaviour Chart (PBC) for Azure DevOps (ADO)

## What is this report? 
This report provides a simple way to analyse the predictability and variation in flow metrics for a team. For the flow metrics of Throughput, Cycle Time, Work In Progress (WIP) and Work Item Age, a Process Behaviour Chart (PBC) is visualized.

The PBC shows what type of variation is present in a teams flow. Any time you see a data point outside of the Upper Natural Process Limit (UNPL) or Lower Natural Process Limit (LNPL), these points highlight a signal that represents exceptional variation. The report contains two pages, page one contains the simplified 'X Chart' and page two contains the 'XmR Chart'. There are two date slicers, one for choosing the baseline range (for calculating UNPL/LNPL), the second for what data you what to compare these values against.

## Why would you use it? 
Separate that which is ‘signal’ from that which is ‘noise' in your data. Variability in terms of Throughput, Cycle Time, Work In Progress (WIP) and/or Work Item Age is inevitable. Understanding when you have too much variability and when an intervention is needed is what is important. Use these charts to find out where you may need to focus. Please note, for flow metrics where the LNPL is not visible, this is because the value is less than 0 which will not be possible for certain metrics (e.g. it is impossible to have a negative Throughput or negative Cycle Time).

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

![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/31a986e1-3ec9-446f-8e6b-1608e7482151)


Azure DevOps Server:

![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/4e47decf-d1e7-4456-9e2b-6a8817308a25)


* Hit 'Load' 
* If you are prompted for a login, you can choose:
  - 'Organizational' and enter your Organization email/password (if required) and sign in
  - 'Basic' and use a Personal Access Token (PAT) to login, entering it in the password field (user can be left as blank - make sure it has 'Read' access to Analytics)

  ![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!
  
<img width="872" alt="Screenshot 2024-01-02 at 14 18 24" src="https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/6018c022-9adc-4434-809e-8f9639f0c1e6">

<img width="871" alt="Screenshot 2024-01-02 at 14 18 42" src="https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/bdb3b7fe-9779-4167-91df-95a1102a0ff3">

## Using the report
There are some key things to look for when visually analysing the charts, things to look for are:
- NOTE: Any items with a cycle time of 0 are automatically excluded
- Any points outside the limits - A single point outside the calculated natural process limits indicates the presence of an exceptional cause that has a dominant effect. Unless it is something seasonal this is the key point to focus on (it’s a ‘signal’).
![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/9e622b1d-c3c1-4dda-99d9-2d2f59da0814)
- Shifts in the process - this can be when points are consistently positioned above/below the average line but then shift. This could allude to something that has changed with regards to the way of working.
- Cyclical/seasonal patterns - this can be when there are particular days or weeks when a shift in values occurs. It may not always mean that this is a ‘signal’.
- The run of ‘eight’ - Eight or more successive values all on the same side of the average may indicate the presence of an exceptional cause that has a weak but sustained effect.
![image](https://github.com/nbrown02/ADO-Process-Behaviour-Chart/assets/29369962/14197c28-fc8b-49eb-83b9-2acf13ec9bdb)
- Runs near the limits - Three out of four successive values all within the upper 25% of the region between the limits, or all within the lower 25% of the region between the limits, may indicate the presence of an exceptional cause that has a moderate but sustained effect.

[Source - Deming Alliance](https://demingalliance.org/resources/articles/process-behaviour-charts-an-introduction)
