# LogicApps
Logic Apps json definitions files. Each app defines a REST API.

- deletealldb: deletes tables departments, hired_employees and jobs from SQL. Not required by the challenge.
  - method: DELETE. 
  - end point: https://prod-15.eastus.logic.azure.com:443/workflows/82cafb7a297c4745be4e87a469f6d750/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=0BwtKqm2d7aK3OnJP-ImyOCtQWsyzM2wwqnej3DdaYk
- employeesHired: returns the values required in point one of Section two.
  - method: GET.
  - end point: https://prod-76.eastus.logic.azure.com:443/workflows/6ea4da02a864460b8c4fbe4390425998/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=_dO5waLmISeuHc78uBah2lByvs-_lIMzxhTTCdy9KFU
  - in path parameter: year. default value 2021.
- globantfileupload: moves data from storage account \file\"file" into SQL table challenge."table", where "file" and "table" are in-body parameters and the body is expected to be in Json format.
  - method: POST.
  - end point: https://prod-31.eastus.logic.azure.com:443/workflows/c18116983e804ff5a31bb0815509dd85/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=RKQlYz3GvKAb4rndjdwe5Vzcs4kFUBecOd3ZwQ4hC-s
  - body example: {"file": "jobs.csv", "table": "jobs"}
  - note: because of the foreign keys hired_employees is the last one to be uploaded.
- mostHiringDepartments: returns the values required in point two of Section two.
  - method: GET.
  - end point: https://prod-01.eastus.logic.azure.com:443/workflows/131caf1661914bf78a56ae79768a808d/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=bEgkAQRqcqOcfSDd5N1DSC7N_67uuxFaebaO_ING5EQ
  - in path parameter: year. default value 2021.
- uploadall: moves data from storage account files \file\jobs.csv, \file\departments.csv and \file\hired_employees.csv respectively into SQL tables jobs, departments and hired_employees. Not required by the challenge.
  - method: POST.
  - end point: https://prod-63.eastus.logic.azure.com:443/workflows/097d6a146b7141f0b23ff46bad420ed9/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=fWbGIxLVCicjhy3irHKdEEAxGMas8RS-s-h5POLW2VQ
