# HCL OneTest UI-WEBUI

This action enables you to run HCL OneTest WEBUI tests.

## Pre requisites

1. Create a github repository
2. Create a folder named ".github/workflows" in the root of the repository
3. Create a .yml file with any name inside the ".github/workflows" folder and you need to copy example in that yml file

## Example usage

```yaml
name: HCL OneTest WEBUI

on: workflow_dispatch

jobs:
    WebUI-Action:
        runs-on: self-hosted
        name: HCL OneTest WEBUI
        steps:
         - name: HCL OneTest WEBUI
           uses: SonaHJ/WebUIAction@main
           with:
            workspace: 
            project: 
            suite: 
            imShared: 
            configFile: 
            swapDatasets: 
            exportReport: 
            exportStats: 
            exportStatsHtml: 
            exportStatsFormat: 
	    exportStatReportList: 
	    imports: 
	    labels: 
	    overwrite: 
	    protocolInput: 
	    publish: 
	    publishFor: 
	    publishReports: 
	    results: 
	    userComments: 
	    varFile: 	    

```
4. Push it into the main branch
5. To configure agent:
    1. Go to settings (Repo).
    2. Select action -> runner.
    3. Click Create self-hosted runner, follow the download and configure instruction

6. Go to the Actions section in the repository and select the workflow.
7. Click the Run workflow dropdown and the list of input boxes get displayed.

## Inputs

### `workspace`

**Required** Complete path to Eclipse workspace.

### `project`

**Required** The name of the project containing the test.	

### `suite`

**Required** Specify the relative path from the project to the test including the file name of the test. A test can be WebUI test, Compound test, Performance schedule or Accelerated Functional Test (AFT) suite. The test suite name must contain the file extension when it is an AFT suite. To run multiple tests from the same project sequentially, you must separate the tests by a colon (:). If you provide multiple tests, you cannot include an AFT suite along with it.

### `imShared`

**Optional** Complete path to HCLIMShared location, if it is not at default location.

### `configFile`

**Optional** The complete path to a file that contains the parameters for a test or schedule run, If Config file is specified then no other fields will be required.

### `swapDatasets`

**Optional** Use this option to replace dataset values during a test or schedule run. You must ensure that both original and new datasets are in the same workspace and have the same column names. You must also include the path to the dataset. For example, /project_name/ds_path/ds_filename.csv:/project_name/ds_path/new_ds_filename.csv

### `exportReport`

**Optional** Use this option to export the unified report of UI tests to the file formats such as PDF, HTML, and XML. For example, to export the report to only the PDF format, you can input "type=unified;format=pdf;folder=Exportedreport102;filename=testreport"

### `exportStats`

**Optional** The complete path to a directory in which to store exported statistical report data.

### `exportStatsHtml`

**Optional** Specify the complete path to a directory in which to export web analytic results. Analyze the results on a web browser without using the HCL OneTest Studio. If you are running multiple tests, do not provide a value in this field. The web analytic results will be exported to Jenkins workspace.

### `exportStatsFormat`
**Optional** Use this field to enter one or more formats for the reports that you want to export by using a comma as a separator. The options are simple.csv, full.csv, simple.json, full.json, csv, and json. When you want to export both simple and full reports in json or csv format, you can specify json or csv as the options. The reports are saved to the location specified in the exportStats field. This field must be used in conjunction with exportStats field.

### `exportStatReportList`
**Optional** You can use this option to specify a comma-separated list of report IDs along with exportstats or exportstatshtml to list the reports that you want to export in place of the default reports, or the reports selected under Preferences. To retrieve the report IDs, navigate to Window > Preferences > Test > Performance Test Reports > Export Reports from HCL OneTest UI and under Select reports to export, select the required reports, and click Copy ID to clipboard.

### `imports`
**Optional** Path of the Project location to be imported. You can also use an empty workspace folder on your computer to import the UI Test project resources and run the tests. 

### `labels`
**Optional** Use this option to add labels to test results. To add multiple labels to a test result, you must separate each label by using a comma.

### `overwrite`
**Optional** Determines whether a result file with the same name is overwritten. The default value, false, indicates that the new result file is created. If the value is true, the file is overwritten and retains the same file name.

### `protocolInput`
**Optional** Use this argument to run a Web UI test in parallel on different browsers.

### `publish`
**Optional** You can use this parameter to publish test results to the Server. The format is: serverURL#project.name=projectName&amp;teamspace.name=teamspaceName.

### `publishFor`
 **Optional** You can use this option to publish the test results based on the completion status of the tests. The supported values are FAIL,PASS,INCONCLUSIVE,ERROR,ALL.

### `publishReports`
**Optional** You can use this option to publish specific test results to the Server. The supported values are FT, STATS, TESTLOG.

### `results`
**Optional** Specify a name for the results file. If you do not specify a name, the test or schedule name appended by the timestamp is used for the name. The results file is stored in the Results directory. If you are running multiple tests, do not provide a name for the results file.

### `userComments`
**Optional** Add text to display it in the User Comments row of the report.

### `varFile`
**Optional** The complete path to the XML file that contains the variable name and value pairs.
