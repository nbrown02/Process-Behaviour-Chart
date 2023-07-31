# Process Behaviour Chart for Azure DevOps

What is this report? 
This report provides a simple way to analyse the predictability and variability of a team. For the flow metrics of Throughput, Work In Progress and Cycle Time, a Process Behaviour Chart (PBC) is visualized.

The PBC (traditionally known as a Statistical Process Control - SPC chart) shows what type of variation is present in a teams flow. Any time you see a data point outside of the Upper Natural Process Limit (UNPL) or Lower Natural Process Limit (LNPL), these points highlight a signal that represents exceptional variation.

Why would you use it? 
Separate that which is ‘signal’ from that which is ‘noise' in your data. Variability in terms of Throughput, Cycle Time and/or Work In Progress (WIP) is inevitable. Understanding when you have too much variability and when an intervention is needed is what is important. Use these charts to find out where you may need to focus. 

When would you use it?
Use this at potentially every other retrospective to understand where there has been variation in your process/ways of working and potentially do some root-cause analysis as to why that may be.

Steps to load the information
Download the template using this link

Open the template in Power BI Desktop

Enter your ASOS ADO Organization / Project / Team Name details in the fields provided:



 

Hit load
Note: you may be asked for a login - follow these steps if it’s your first time

Then your data is loaded


Using the report
There are some key things to look for when visually analysing the charts, things to look for are:

Any points outside the limits - A single point outside the calculated natural process limits indicates the presence of an exceptional cause that has a dominant effect. Unless it is something seasonal this is the key point to focus on (it’s a ‘signal’).



 

Shifts in the process - this can be when points are consistently positioned above/below the average line but then shift. This could allude to something that has changed with regards to the way of working.

Cyclical/seasonal patterns - this can be when there are particular days or weeks when a shift in values occurs. It may not always mean that this is a ‘signal’.

The run of ‘eight’ - Eight or more successive values all on the same side of the average may indicate the presence of an exceptional cause that has a weak but sustained effect.



Runs near the limits - Three out of four successive values all within the upper 25% of the region between the limits, or all within the lower 25% of the region between the limits, may indicate the presence of an exceptional cause that has a moderate but sustained effect.

(Source - Deming Alliance)
