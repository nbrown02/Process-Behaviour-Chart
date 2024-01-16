# Process Behaviour Chart (PBC) for Azure DevOps (ADO) & Jira (Cloud)

## What is this report? 
This report provides a simple way to analyse the predictability and variation in flow metrics for a team, inspired by Dan Vacanti's book, [Actionable Agile Metrics Volume II - Advanced Topics in Predictability](https://leanpub.com/actionableagilemetricsii).

For the flow metrics of Throughput, Cycle Time, Work In Progress (WIP) and Work Item Age, a Process Behaviour Chart (PBC) is visualized.

The PBC shows what type of variation is present in a teams flow. Any time you see a data point outside of the Upper Natural Process Limit (UNPL) or Lower Natural Process Limit (LNPL), these points (shown as a red dot) highlight a signal that represents exceptional variation. The report contains two pages, page one contains the simplified 'X Chart' and page two contains the 'XmR Chart'. There are two date slicers, one for choosing the baseline range (for calculating UNPL/LNPL/URL), the second for what data you what to compare these values against.

## Why would you use it? 
Separate that which is ‘signal’ from that which is ‘noise' in your data. Variability in terms of Throughput, Cycle Time, Work In Progress (WIP) and/or Work Item Age is inevitable. Understanding when you have too much variability and when an intervention is needed is what is important. Use these charts to find out where you may need to focus. Please note, for flow metrics where the LNPL is not visible, this is because the value is less than 0 which will not be possible for certain metrics (e.g. it is impossible to have a negative Throughput or negative Cycle Time).

## When would you use it?
Use this at potentially every other retrospective to understand where there has been variation in your process/ways of working and potentially do some root-cause analysis as to why that may be.

### Prerequisites
* [Make sure you have the latest version of Power BI Desktop](https://aka.ms/pbiSingleInstaller)
* Download the appropriate template file:
  - [Azure DevOps / Azure DevOps Server / TFS version](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/raw/main/Capacity%20Planning%20&%20Feature%20Monte%20Carlo%20(ADO).pbit)
  - [Jira version](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/raw/main/Capacity%20Planning%20&%20Feature%20Monte%20Carlo%20(Jira).pbit) 
* Create/save an access token 
  - [Personal Access Token (PAT) if using Azure DevOps (make sure you have 'Read' Analytics access)](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows)
  - [Jira API token if using Jira](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)
* Then you're good to get started!

### Connectivity (Azure DevOps Version)
* Open the .pbit file in Power BI Desktop
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization, project name and team name

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

![PBCGIF](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/3d21d502-b1c2-464a-8ce7-15a3156c8889)

![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/4bf72597-c0c3-4a7e-816c-3e27dabee6d5)

### Connectivity (Jira Version)
* Open the .pbit file in Power BI Desktop
* Add your Jira URL 
* Add your Jira Project Key 

Don't confuse the project name with the project key, a common mistake! Your project key will be in the URL when viewing an item.

* It should then look something like this:
![image](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/assets/29369962/2a24cc23-d6d5-4768-9bcf-12e6bf27bc58)

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your email associated with your Jira account for your username
  - Your API token you created in the Prerequisities

![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz-Jira/main/Screenshots/Login2.png)

* Then hit 'Connect' and wait for the data and charts to load!

## Using the report
There are some key things to look for when visually analysing the charts, things to look for are:
- NOTE: Any items with a cycle time of 0 are automatically excluded
- Large Changes (any points outside the Upper Natural Process Limit (UNPL) | Lower Natural Process Limit (LNPL)) - Any data point outside of the natural process limits (UNPL/LNPL). Unless it is something seasonal this is the key point to focus on (it’s a ‘signal’). These will be highlighted as a red dot.
  
  ![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/e1647e06-14c8-474d-9dc5-7e6fbcf44e63)

- Moderate changes - Any data point with a run of 3 items with 2 out of any 3 consecutive points within the process limits are above the 2-sigma line. These will be highlighted as an orange dot.
  
  ![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/11c41cd5-a645-4a3b-a2de-8e5db9142ec4)

- Moderate shifts - Any data point with a run of 5 items where 4 out of any 5 consecutive points within the process limits are above the 1-sigma line. These will be highlighted as a light orange dot.

  ![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/74d40460-30b4-4be7-86b1-24da2185c3f9)

- Small shifts - Any data point with a run of at least 8 successive values within the process limits on the same side (above or below) the average

  ![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/276221a2-d95d-4ec3-9ba9-4dd41da9222a)

- Similarly, in the XmR chart page you can apply the same filters however there will also be a red dot any time the mR chart value exceeds the Upper Range Limit (URL)

  ![image](https://github.com/nbrown02/Process-Behaviour-Chart/assets/29369962/2faff639-0b30-4140-a49c-5dc3917cfddf)


