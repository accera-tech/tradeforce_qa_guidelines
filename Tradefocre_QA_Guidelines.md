# Accera’s Quality Assurance Guidelines

- Start Date: 2019-03-27
- Version: 0.1.0-DRAFT
- Last Editor: Leonardo Giordani

## Summary
The purpose of this guide is to introduce how does the Quality Assurance area is structured, how we are organized as a team, which tools we use and how to install/configure it. Also, you’ll be introduced to what is our actual goals to achieve a higher customer satisfaction over the products we are testing.

## Table of Contents
- [Summary](#summary)
- [What is Trade Force](#WhatisTradeForce)
- [How we work](#Howwework)
- [Software and Tools](#SoftwareandTools)
- [Code](#Code)
- [Our goal as a team](#Ourgoalasateam)

## What is Trade Force

Trade Force is an application which allows our customers to gather details and a huge amount of data by to check-in marketplaces using they’re mobile devices. All the data is sent to the web portal on where the managers can process this data and get valuable information, which allows them to take intelligent actions.

As described above, Trade Force operation is composed by mobile App and web application. Look at the mind maps below, which describes the function of each menu and its ramifications over screens.

<img width="796" alt="tradeforce-portal" src="https://user-images.githubusercontent.com/48480786/55908324-7c0ad580-5baf-11e9-8177-b81de2d75ee4.png">

<img width="690" alt="tradeforce-mobile" src="https://user-images.githubusercontent.com/48480786/55908355-9349c300-5baf-11e9-864d-42aa019f7cfb.png">

## How we work

Today we use the agile technics of Kanban and we also write the code using BDD format. For the future, after start developing test scripts, we envision to make scenario and code review at each other’s.
Our main ceremonies are: 

- Daily meeting 
> Each composer of the team should say what is he working today and if there’s any blockers, so the team can organize a strategy to overcome it;

- Planning meeting
> Organized by the PO of the project and in this meeting the team will plan the features and other deliverables that will be a part in the next release; In this meeting, the team will estimate the efforts in ours to conclude each Story and if necessary, the Story will be broken into smaller tasks and someone should be assigned as the responsible for the Story. In this ceremony, it’s also important to talk to the team, solve any doubts and prioritize the Stories.

- Releases
> For the mobile app, currently is generated a release per month, as for the web portal, the release is generated when its deliverables are not just bug fixes but contains some new features. Regression tests are very important at this scenario.

- Retrospective meeting 
> Is when the whole team meets to discuss the following points regarding the last sprint: What went well, what was not good and what we can do to improve the process. In this meeting, QA team will showcase the deliverables to the team and specially to PO and product team.  

Currently our process is:

<img width="709" alt="processodeteste" src="https://user-images.githubusercontent.com/48480786/55912649-88942b80-5bb9-11e9-94e5-ae632863aaf9.png">

Our goal as a team is to reach the below process, which embraces agile technics like code review. Automated test scripts are written based on the information available in the user stories so we can start developing the test scripts at the same time as the dev team implements the functionalities. So, by the time the dev team finishes the functionalities implementing, our test scripts should be done.

<img width="625" alt="processocompleto" src="https://user-images.githubusercontent.com/48480786/55912904-c3965f00-5bb9-11e9-99fb-52fb67031b9e.png">

In order to have a better test coverage and the best possible test scripts, by following the process on above image, the test scenarios review shouldn’t be made by the person who wrote it, the same value for the test scripts review.

### Jira

Currently is the tool used to organize all our deliverables and follow the Kanban approach. Our job is to get the stories from the “TIP” tab and follow the flow:

1.	Understand all business rules and features of the story
2.	Write the test scenarios using cucumber
3.	Upload the test scenarios on Github and share the link with QA, Dev and Products team
    * The test scenarios should be reviewed by a QA team member
4. Develop the test scripts
    * The test scripts should be reviewed by a QA team member
5. Test execution
    * If all tests ends successfully, all the test evidences should be available for Dev and Products team
    * The Story must be put on DONE tab
    * If there’s any error on the test execution, all the test evidences should be available for Dev and Products team
    * The Story must be put on REOPENED tab
    
When an error is found in the test execution, It must be logged to the respective Story as a comment, following the format (repeat it for each error found in the test execution):

| Jira comments section |
| --- |      
| [Description of the error found] |
|•	Android version |
|•	App version |
|[Steps to reproduce the error] |
|1. Step 1 |
|2. Step 2 |
|3. Step 3… |
|Attach a screenshot or log file generated on the failing execution. |      

After Dev team fix the issue, the respective Story should be put again on TIP tab ONLY after the deploy of the correction is done. As QA team we expect the following info in the comments section of the Story:
-	Which error was fixed;
-	App version containing the correction;

## Software and Tools

Quality Assurance team perform automated tests on Tradeforce’s mobile App to the web portal and also the data flow thru APIs. All defects and new features from this software is also tested by QA team.
Our current test structure is assembled below:

<img width="380" alt="structure" src="https://user-images.githubusercontent.com/48480786/55990243-9ca16100-5c7d-11e9-8cf1-ea38f7df7e95.png">

Here’s the software and tools in use:
-	IntelliJ IDEA Community Edition
-	Appium
-	Microsoft SQL Server Management Studio
-	Android Studio
-	Postman
-	Nodejs

Tools
-	Jira
-	Slack
-	Github
-	TeamCity
-	Feature Express

Get the software from:

-IntelliJ IDEA Community Edition:
https://www.jetbrains.com/idea/download/#section=windows

-Appium
http://appium.io/

-Android Studio
https://developer.android.com/studio/?hl=pt-br

-Postman
https://www.getpostman.com/downloads/

-Nodejs (only used to download Feature Express tool)
https://nodejs.org/en/

-Microsoft SQL Server Management Studio and Jira access should be provided by IT team.

-To access Team City tool, refer to the link below and always log in as Guest.
http://177.71.246.7:8080/overview.html

The automated test scripts are developed in java using cucumber framework, but we also apply manual tests on several occasions, to do it on Mobile we have the following test only mobile phones physically in the office:

| Model | Android Version |
| --- | --- |     
| LG-X230ds | 6.0 |
| Galaxy J2 Prime | 6.0.1 |
| Galaxy Note3 | 5.0 |
| Galaxy A5 | 8.0 |
| Moto E4 | 7.1.1 |

There’s a lot more models available but it’s divided by QA and Dev team, for further information, check the [Link](https://accerasuplychain-my.sharepoint.com/:x:/r/personal/maycon_cardoso_accera_com_br/_layouts/15/Doc.aspx?sourcedoc=%7B3ccb3e98-78f2-47b7-9ca4-7174b8cfb91c%7D&action=default&cid=61f681ac-4087-4fa3-842d-c7217c69fe12).

## Code

To be able to develop faster test scripts using cucumber, it’s recommended to use Karate framework. Please read it’s documentation on github: https://github.com/intuit/karate.

Our test suite should implement the page objects design pattern which consists in a BasePage on which it’s implemented all general methods used by the whole project and is where we can configure the access to the system.
We define a Page class on where all objects related to the page in test is defined and the methods to interact to this screen.
The Flow class is used to generate the proper test methods by accessing the objects defined on the Page class. Basically the Flow class is where we can interact with the page objects.

Name patterns
Docs, Files and Folders should follow the company standards.

## Our goal as a team

First and foremost, our main goal is to always deliver a high-quality product by exploring the most of the skills and creativity of our team members, and at every version, enhance the user experience and so customer satisfaction.
