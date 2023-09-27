# workflow-loadtesting-sample
This simple Jmeter testplan is used to simulate concurrent users on Workflow / CloudPak for Business Automation who interact with the Hiring Sample, a simple process application that is part of a typical Workflow installation. 

JMeter is a simple and free test tool that is easy to use and sufficient for a first dive into performance testing. Especially for REST based test plans, JMeter offers the basic functionality to simulate concurrent users interacting with the system. For more information about JMeter refer to https://jmeter.apache.org/.

The Hiring Sample  process application includes a process called “HR Open New Position”, which captures the steps and decision points for submitting and processing a request to fill a job position. The testplan creates a new instance of the Hiring Sample process and then navigates this instance until all steps have been completed.

Follow the steps below to run the Jmeter testplan against the Hiring Sample on Workflow:

* Make sure the Hiring Sample is installed on your Workflow installation: https://www.ibm.com/docs/en/baw/22.x?topic=tutorials-instructions-running-hiring-sample-process-application
* Install Jmeter on a client machine: https://jmeter.apache.org/download_jmeter.cgi
* Download the jmx and csv files on your client machine
* Load the testplan HiringSample.jmx into JMeter
* Modify the user defined variables to match your environment and the load you want to produce. ProcessAppId and bpdId match the HiringSample.
* Modify the UserPassword.cvs to match your environment. Ideally you have defined in the cvs the same amount of users as defined for the numberOfThreads setting in the User defined variables
* Each step that simulates a user interaction has a think time defined. Think time influences, beside the number of user threads, the load you produce. Take this into consideration and modify the think time to your needs.
* Execute the testplan and review the test execution in the Result Tree view and gather throughput and response time statistics in the Aggregate Graph view.  
