# Checking the Status of SQL Server Agent Jobs #

One of the checks I like to do at the start of each day is to look at the status of all SQL agent jobs that ran overnight. However it can be time consuming to do this, especially if you have a lot of servers. Below I've outlined some scripts that I run against each production server in order to perform these checks. 


## Getting a Complete Job History ##

The **JobHistory24.sql** script lists all jobs run in the last 24 hours, along with the time run, the outcome, and whether the job is enabled.

This uses the sysjobhistory and sysjobs system tables in the msdb database. One curious aspect of these tables is that they store dates and times as a numerical respresentation of a time and date such as 20160417. To make this more readable I've converted this into a more conventional format


