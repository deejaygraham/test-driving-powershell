Approximately 30-40 minutes code demo.

### Beginning

Start with Scratch code

Add Import Module, Describe and It. Note placement of curly brackets not optional.

Run and show ? no tests actually found

Add first assertion 'toast' | Should Be 'test'. Left hand object to inspect, right hand assertion. Many other assertions are available.

Success and failure and formatting of output. Its stack up inside a single describe block.

### Infrastructure Testing

Use Invoke-WebRequest to retrieve a web page (get or head) and use Select-Object -ExpandProperty to inspect the status code. Create a list of urls and iterate through them (ForEach-Object) within a describe block and use each item in an It to test the individual url. Gives list of urls tested and shows which of them work, which do not.  

### API Testing

Star Wars is a thing. Star Wars even has an API to query people, planets, films etc. Create a .Tests.ps1 file for each resource to test Gets. Move base uri into a parameter to each script and have the controller script pass it to each one. Use Invoke-Pester with wildcard to run all scripts. 

### CI Builds

CI can be supported by asking Invoke-Pester to generate an output file in a common format. Use NUnitXml so that most CI platforms - TFS, VSTS, Jenkins etc. will understand and can create graphs and charts of passes and fails.

### Tagging

Use Invoke-Pester with -Tag 'Regression'. Note all tests are examined but nothing run. Add Tag to one description and show that runs. 

### Christmas-Driven Development

Christmas is important time of year if you are the Grinch or Richard Attenborough. Wrote a module full of Christmas functions and at .Test.ps1 file to go along with it. All tests are broken at the moment. Will go through and make them work.

Cardinal sin - need to write to file system because function expects a file. Dependencies like this can be file system, network, internet, databases, clocks and dates. File system can be mitigated by the use of $TestDrive as a path. Created temporary folder on entry to each new Describe block and destroyed afterwards. Makes tests more resilient to order of running and stops false positives and negatives. 

### Code Coverage

Work out what code is being called and what isn't by using -CodeCoverage parameter to Invoke-Pester. Shows table of uncalled code at end of run. Select the code module not the test file. 

### Mocks

How long to christmas? Can't get consistent results from a live web site (no API for xmas). Mock a web page returning function.
Mocks give independence and control, the mocked function is replaced and not executed. Issues on Mac OS and PSCore not mocking some featrues or doing it unreliably - maybe down to the session?

Mock external dependencies and anything that gets in the way of running the function you want to test. Created and destroyed in smallest scope - either at the context level or describe level. It blocks share mocks.

Mocks can be stacked up and selected from top to bottom based on given parameters. Get-Date won't work on Mac OS.  Use Assert-MockCalled to make sure your mock is being called instead of real function. 

Test private functions not exposed by a module by using InModuleScope.



