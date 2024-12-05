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

