# Jamal's Absense Training

## Monitor Commissions Runs
Check the Processor.RunHistory table for errors.  Cross reference the error log table to get the stack trace.  Use that to zero in on the SPs that are causing the problems.

## Downgrades
Paul Kim does this around the 12th or 13th of the month.  If there are problems go to the Phoenix portal and "Run Downgrade Consultants" under Commissions.  Performance.GetAccountsToDowngrade is the SP that's used to find the count of consultants who need to be downgrade.  Processor.RunHistory also records runs of this.  If something fails, just have him try running it again. (Don't do it yourself to avoid having multiple jobs running simultaneously)

## Month End
Steps:

* Push the "Run Bonus Run" button on the commissions page.
  * They sit on this for a day or two and verify data.  They'll come back to our team to address any issues.
  * ProcessorService.cs -> BonusRun()
* Push the "Run Publish Run" button on the commissions page.
	Closes out the period and moves the data from the Prep schema table to the dbo Schema tables.

## 30 Minute Commission Run
ProcessorService.cs -> PerformanceRun()

## CommissionsAPI
This is the API that serves data from the commissions DB to nogento.

Usually just work off of master.

Caching used to just load all the data into memory.
CommissionsService.cs -> SearchCalculations is an example of the new caching scheme.

ec2-3-89-248-35.compute-1.amazonaws.com or comm-api-stg - Staging Commissions API Server
ec2-54-242-235-230.compute-1.amazonaws.com or comm-api-prd-1 - Production Commissions API 