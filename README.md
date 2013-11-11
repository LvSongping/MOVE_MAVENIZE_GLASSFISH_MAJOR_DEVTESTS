#How to run the dev test cases
================================
#Annotation: 
These tests are used to test the GLASSFISH's deployment, ejb container, security, webtire and admin.
Nowadays, Most of the test suits are still being moved and mavenized excepted the deployment component.


#Preparation and Steps:
1). Ensure your system have installed maven which version is above 3.0.4.

2). Make sure you have installed the JDK which version is ablve 1.7_09.

3). Make sure you have installed the GLASSFISH v4.

4). Checkout the tests suit form the github https://github.com/LvSongping/MOVE_MAVENIZE_GLASSFISH_MAJOR_DEVTESTS

5). Set the following env. variables as below:

        S1AS_HOME=<glassfish v4 installation>
        APS_HOME=<appserv-tests>

6). Check the following env. variables to set with these values:

		SECURE=false
		DEPL_TARGET=PE
		Nothing needs to be done if you don't have these env. var set.

4). Start the domain.

		asadmin start-domain -v 

5). Simply type "mvn install" from devtests/deployment.  At the end
    of the run, in the above mentioned directory two files are created :
    result.html has the result of each test; client.log has all output from test run

6). To run individual tests, go to the test directory and type "mvn install". For
    example, to run war/servletonly test "cd war/servletonly" and do "mvn install".
    The results.html and client.log are created in war/servletonly directory



READING RESULTS :
-----------------

1. result.html will state whether a particular test passed or failed. This
   file just has a summary of the test results.
2. compare results with EXPECTED_RESULTS.txt, grep for "FAILED", "UNKNOWN" to see if any test has failed.
