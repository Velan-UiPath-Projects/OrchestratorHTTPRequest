This is a demo use case to trigger a process via Orchestrator API.

1.	Identify the process key.

Sequence  : GetProcessId.xaml
API : /odata/Releases?$filter=%20Name%20eq%20'all_activities_DocEnv'
Method : Get
Reference : https://docs.uipath.com/orchestrator/standalone/2022.10/api-guide/processes-requests

2.	Trigger the Process by input the process key.

Sequence : StartJob.xaml

API : /odata/Jobs/UiPath.Server.Configuration.OData.StartJobs
Method : POST
Payload :

"{  startInfo: {    ReleaseKey:’process Key taken from step 1’,    'Strategy': 'ModernJobsCount',    'RobotIds': [],    'NoOfRobots': 0  }}"

Reference : https://docs.uipath.com/orchestrator/standalone/2022.10/api-guide/jobs-requests
