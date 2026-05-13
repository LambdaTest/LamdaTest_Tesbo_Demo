# Run Selenium Tests With Tesbo — TestMu AI (Formerly LambdaTest)

![image](https://user-images.githubusercontent.com/70570645/171464306-1da0360c-de4f-40a0-817a-1855088553b9.png)

<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn how to use Tesbo framework to configure and run your automation testing scripts on the TestMu AI platform*

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)

## Table of Contents:


* [Prerequisites](#prerequisites)
* [Running The Tesbo Test Automation Script On Online Selenium Grid](#running-the-tesbo-test-automation-script-on-online-selenium-grid)
* [Performing Parallel Testing With Online Selenium Grid](#performing-parallel-testing-with-online-selenium-grid)

## Prerequisites

* You would need Java development environment i.e. JDK 1.6 or higher. We recommend using the latest version.
* An IDE (Integrated Development Environment) such as Eclipse or IntelliJ.

## Running The Tesbo Test Automation Script On Online Selenium Grid


After you download or clone the TestMu AI-Tesbo Repository, you will find the test folder which would have your test files by the name [CheckBox.tests](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/src/test/java/tests/CheckBox.tests) & [FormsAndList.tests](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/src/test/java/tests/FormsAndList.tests).

>**Test Scenario**: The CheckBox.tests file tests Check all button functionality whereas the FormsAndList.tests file tests AJAX input forms functionality.

Now that you have your test scripts ready with you, a few edits to the `config.json` is all that is required to run your test files over TestMu AI Selenium Grid. 

Let's have a look at how to edit these files.

**Step 1:** You need to specify the Selenium Address in your `config.json` that would point your tests to the Hub URL of TestMu AI Selenium Grid. Your Selenium Address would be:

```javascript
https://{LambdaTest_Username}:{LambdaTest_Access_Key}@hub.lambdatest.com/wd/hub
```

**Step 2:** In your `config.json` there is a config called "**IsGrid**". By default, IsGrid is set to false, make sure you set it as **true**.

```javascript
"IsGrid": true
```
**Step 3:** Define your desired capabilities. By defining your desired capabilities, you are informing the TestMu AI Selenium Grid about the configurations over which you wish your test automation script to run. You can take help from TestMu AI [Desired Capability Generator](https://www.testmuai.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo) to fetch the capabilities class.

![1-4d66a8cd468232f272009c1dda3a7f87](https://user-images.githubusercontent.com/70570645/170709877-d2856f3f-1b16-4a2b-bcd4-e2759ded09b6.png)

Check out the complete [config.json](https://github.com/LambdaTest/LamdaTest_Tesbo_Demo/blob/master/config.json) file.

Now just hit the run button and you will find your test automation scripts running over the TestMu AI Selenium Grid.

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
## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe.

## Documentation & Resources :books:

Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo)  
      
 ## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=LamdaTest_Tesbo_Demo) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com)

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

**🔄 Our Rebrand Journey**

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

**🔭 Explore TestMu AI**

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)