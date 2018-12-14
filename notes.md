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

