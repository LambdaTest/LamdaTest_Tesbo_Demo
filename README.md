# Selenium Automation Testing With Tesbo On LambdaTest

![image](https://user-images.githubusercontent.com/70570645/171464306-1da0360c-de4f-40a0-817a-1855088553b9.png)

<p align="center">
  <a href="https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/c/LambdaTest" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn how to use Tesbo framework to configure and run your Java automation testing scripts on the LambdaTest platform*

## Table of Contents:


* [Prerequisites](#prerequisites)
* [Running The Tesbo Test Automation Script On Online Selenium Grid](#running-the-tesbo-test-automation-script-on-online-selenium-grid)
* [Performing Parallel Testing With Online Selenium Grid](#performing-parallel-testing-with-online-selenium-grid)

## Prerequisites

* You would need Java development environment i.e. JDK 1.6 or higher. We recommend using the latest version.
* An IDE (Integrated Development Environment) such as Eclipse or IntelliJ.

## Running The Tesbo Test Automation Script On Online Selenium Grid


After you download or clone the LambdaTest-Tesbo Repository, you will find the test folder which would have your test files by the name [CheckBox.tests](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/src/test/java/tests/CheckBox.tests) & [FormsAndList.tests](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/src/test/java/tests/FormsAndList.tests).

Now that you have your test scripts ready with you, a few edits to the `config.json` is all that is required to run your test files over LambdaTest Selenium Grid. 

Let's have a look at how to edit these files.

**Step 1:** You need to specify the Selenium Address in your `config.json` that would point your tests to the Hub URL of LambdaTest Selenium Grid. Your Selenium Address would be:

```javascript
https://{LambdaTest_Username}:{LambdaTest_Access_Key}@hub.lambdatest.com/wd/hub
```

**Step 2:** In your `config.json` there is a config called "**IsGrid**". By default, IsGrid is set to false, make sure you set it as **true**.

```javascript
"IsGrid": true
```
**Step 3:** Define your desired capabilities. By defining your desired capabilities, you are informing the LambdaTest Selenium Grid about the configurations over which you wish your test automation script to run. You can take help from LambdaTest [Desired Capability Generator](https://www.lambdatest.com/capabilities-generator) to fetch the capabilities class.

![1-4d66a8cd468232f272009c1dda3a7f87](https://user-images.githubusercontent.com/70570645/170709877-d2856f3f-1b16-4a2b-bcd4-e2759ded09b6.png)

Check out the complete [config.json](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/config.json) file.

Now just hit the run button and you will find your test automation scripts running over the LambdaTest Selenium Grid.

## Performing Parallel Testing With Online Selenium Grid

You can leverage parallel testing to run multiple tests at the same time. To run parallel testing with Tesbo framework, you need to specify the count of parallel test in the config.json & set the parallel status to true.

```javascript
 "parallel": {
      "status": true,
      "count": "3"
    },
```

Now, if you wish to perform cross browser testing using the same script over different browsers in parallel then you need to define more capabilities in the config.json. 

Let's run the same script on three different browsers, simultaneously. We will run the script on Google Chrome 81 & Mozilla Firefox 76 on Windows 10. For macOS, we will take Safari 13.

```javascript
"capabilities": {
      "chrome": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "Windows 10",
        "browserName": "Chrome",
        "version": "83.0"
      }
 
      "firefox": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "Windows 10",
        "browserName": "Firefox",
        "version": "76.0"
      }
      "safari": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "MacOS Catalina",
        "browserName": "Safari",
        "version": "13.0"
      }
    },
```

Here is the new config.json to run parallel testing with Tesbo & LambdaTest.

```javascript
{
  "run": {
    "baseUrl": "https://www.seleniumeasy.com/test/",
    "seleniumAddress": "https://{userName}:{ApiKey}@hub.lambdatest.com/wd/hub",
    "by": {
      "tag": [
        "FO1"
      ]
    },
    "browser": {
      "name": [
        "chrome"
      ]
    },
    "capabilities": {
      "chrome": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "Windows 10",
        "browserName": "Chrome",
        "version": "83.0"
      }

      "firefox": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "Windows 10",
        "browserName": "Firefox",
        "version": "76.0"
      }
      "safari": {
        "build" : "Tesbo_With_LambdaTest",
        "name" : "Tesbo",
        "platform": "MacOS Catalina",
        "browserName": "Safari",
        "version": "13.0"
      }
    },

    "parallel": {
      "status": true,
      "count": "3"
    },
    "retryAnalyser":{
      "count":"0"
    },
    "binaries": {
      "chrome": ""
    },

    "highlightElement": true,
    "IsGrid": false
  },

  "cloudIntegration" : {
    "report": false,
    "apiKey": "d31129abe90e5e2086e56a26995cc1cc",
    "projectKey" : "5cd2e1f802d39139e8bf5092",
    "buildName":"QAbleTest001"
  }
}
```
## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe.

## Documentation & Resources :books:

Visit the following links to learn more about LambdaTest's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [LambdaTest Documentation](https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)
* [LambdaTest Blog](https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)
* [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)  
      
 ## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At LambdaTest ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/) 
      
## About LambdaTest

[LambdaTest](https://www.lambdatest.com?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo) is a leading test execution and orchestration platform that is fast, reliable, scalable, and secure. It allows users to run both manual and automated testing of web and mobile apps across 3000+ different browsers, operating systems, and real device combinations. Using LambdaTest, businesses can ensure quicker developer feedback and hence achieve faster go to market. Over 500 enterprises and 1 Million + users across 130+ countries rely on LambdaTest for their testing needs.    

### Features

* Run Selenium, Cypress, Puppeteer, Playwright, and Appium automation tests across 3000+ real desktop and mobile environments.
* Real-time cross browser testing on 3000+ environments.
* Test on Real device cloud
* Blazing fast test automation with HyperExecute
* Accelerate testing, shorten job times and get faster feedback on code changes with Test At Scale.
* Smart Visual Regression Testing on cloud
* 120+ third-party integrations with your favorite tool for CI/CD, Project Management, Codeless Automation, and more.
* Automated Screenshot testing across multiple browsers in a single click.
* Local testing of web and mobile apps.
* Online Accessibility Testing across 3000+ desktop and mobile browsers, browser versions, and operating systems.
* Geolocation testing of web and mobile apps across 53+ countries.
* LT Browser - for responsive testing across 50+ pre-installed mobile, tablets, desktop, and laptop viewports

    
[<img height="70" src="https://user-images.githubusercontent.com/70570645/169649126-ed61f6de-49b5-4593-80cf-3391ca40d665.PNG">](https://accounts.lambdatest.com/register)


      
## We are here to help you :headphones:

* Got a query? we are available 24x7 to help. [Contact Us](support@lambdatest.com)
* For more info, visit - https://www.lambdatest.com?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo
