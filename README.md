# Power Bi Report
Power BI Dashboard for Tracking Student Progress and Performance: Global
Careers


## Combined folder
_Combined the folders of the AWS and Power Bi_
The folder contains the combined folders of the excel and csv files from both tracks(i.e PBI for Power Bi and AWS
 for Cloud Training)


## Created a column for the dropout individuals 
_Use this dax code to create the dropout-status_: 
`Dropout_Status = 
IF(
    AND(
        PowerBI_status[Certification Status] = "Not Certified", 
        PowerBI_status[Graduation Status] = "Non Graduate"
    ), 
    "Dropout", 
    "Non Dropout"
)` for the PowerBi table

`Dropout_Status = 
IF(
    AND(
        AWS_status[Certification Status] = "Not Certified", 
        AWS_status[Graduation Status] = "Non Graduate"
    ), 
    "Dropout", 
    "Non Dropout"
)` for the Cloud training table
 

This will create a new column that will the condition, if the person is not certified and is not a graduate.
The person will be regarded as a dropout or the otherwise.

## Created a column in the zoom attendance
'Duration2 = 'zoom attendance'[Leave Time]-'zoom attendance'[Join Time]'

## Created a column in the zoom attendance for the attendance
'Attendance = if('zoom attendance'[Duration2]>=time(0,30,0),1,0)'
