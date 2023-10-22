# LogicApps
Logic Apps json definitions files. Each app defines a REST API hosted in Azure Logic Apps triggered "When a HTTP request is received".

- deletealldb: deletes tables departments, hired_employees and jobs from SQL. Not required by the challenge.
  - method: DELETE. 
  - end point: https://prod-15.eastus.logic.azure.com:443/workflows/82cafb7a297c4745be4e87a469f6d750/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=0BwtKqm2d7aK3OnJP-ImyOCtQWsyzM2wwqnej3DdaYk
- employeesHired: returns the values required in point one of Section two.
  - method: GET.
  - end point: https://prod-76.eastus.logic.azure.com:443/workflows/6ea4da02a864460b8c4fbe4390425998/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=_dO5waLmISeuHc78uBah2lByvs-_lIMzxhTTCdy9KFU
  - in-path parameter: year (default value: 2021).
- globantfileupload: moves each file passed into the body-parameter list "files" from storage account container \file into the corresponding SQL table under the schema challenge.
  - method: POST.
  - end point: https://prod-31.eastus.logic.azure.com:443/workflows/c18116983e804ff5a31bb0815509dd85/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=RKQlYz3GvKAb4rndjdwe5Vzcs4kFUBecOd3ZwQ4hC-s
  - body example: {"files": ["departments", "jobs", "hired_employees"]}
  - note: files will be updated in the same order they were passed in the list. Because of the foreign keys, hired_employees should be the last one to be uploaded.
- mostHiringDepartments: returns the values required in point two of Section two.
  - method: GET.
  - end point: https://prod-01.eastus.logic.azure.com:443/workflows/131caf1661914bf78a56ae79768a808d/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=bEgkAQRqcqOcfSDd5N1DSC7N_67uuxFaebaO_ING5EQ
  - in-path parameter: year (default value: 2021).
