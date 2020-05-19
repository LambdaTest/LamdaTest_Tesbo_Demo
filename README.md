# LamdaTest_Tesbo_Demo

This Project Included the Configuration to run Tesbo Test on the [LamdaTest](https://www.lambdatest.com/selenium-automation) : A test execution platform, which offer 2000+ browsers & OS to run tests on


#### How to Run Tesbo Test On Lamda Test : 

1. Open Config.json
2. Setup Selenium address key 

 ```
 "seleniumAddress": "https://{UserName}:{AccessToken}@hub.lambdatest.com/wd/hub",
```

*Note* : get your LamdaTest username and Access Token from your LamdaTest Account and Set it as a given formate

3. Set "IsGrid" Config to 'true'
   - This will switch the Tesbo to run Test on LamdaTest from Local
   
4. Define Desired Capabilities in Config file
   - You can generate capability from here : https://www.lambdatest.com/capabilities-generator/
   
5. Run The Test.

6. Whoooo!!!!! Go and Check on LamdaTest Dashboard, Test are already running there!!!!.....
