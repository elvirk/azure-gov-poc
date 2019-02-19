# QnA/LUIS Sample

This guide is a step-by-step instruction for creating a QnA Maker-like solution in Azure Gov using LUIS and the Bot Framework.
See the included Visio diagam ```architectural diagram.vsdx``` for an architectural overview of this solution.

## Create Resources in Azure Gov
1. Create a Resource Group

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20rg.jpg)

2. Create LUIS Instance

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20luis.jpg)

3. Create Bot Framework App

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20web%20app%20bot.jpg)

## Configure LUIS
1. Login to the LUIS applications portal (https://luis.azure.us/applications)
2. Open up the LUIS application that was created during the bot framework app deployment

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/luis%20app.png)

3. Click "Create New Intent"
- Name the intent after the question you want answered
- This should be a unique "key value" that you can reference to tie to a response later

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/new%20intent.png)
![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/whatisazure.png)

4. After creating a new Intent, add different Utterances that are derivatives of the question you want
- For example, you might type in "What is Azure?", "Azure basics", "Tell me about Azure", etc.
- This helps train the model to direct different questions to the appropriate single response

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/whatisazure-intent.PNG)
![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/whatisazure-more-intents.PNG)

5. Repeat steps 3-4 for any other Intents (questions) that you want LUIS to understand
6. When you are done, at the top right click "Train" to train the LUIS model based on the input Intents and Utterances
7. Click "Publish" to make the LUIS endpoint available to the Bot Framework app

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/train-publish.png)

## Develop and Deploy Bot Framework App
1. In Azure, open up the Web App Bot that was previously created

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/bot-rg.PNG)

2. Once inside the Web App Bot, click the Build tab and then Download Bot source code

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/bot-download.PNG)

3. Extract the downloaded .zip and open up the ```BasicBot.sln``` file in Visual Studio
4. Inside of the solution, open up ```BasicBot.cs```

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/sample-bot.png)

- This is where any custom code changes will be made to make the bot differ from the demo bot supplied by Azure
5. Replace the code inside of the ```BasicBot.cs``` in Visual Studio with the code inside of ```BasicBot.cs``` included is this GitHub repository to continue the demo
- Please note that this is very basic and only supports 1-level questions and answers
- Custom development will be required to enhance this solution further
6. Publish the new application to the Web App Azure created previously

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/publish.png)

## Configure Bot App with Questions and Answers
1. In Azure, open up the Web App Bot that was previously created
2. Once inside the Web App Bot, click the Application Settings tab

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/new-setting.PNG)

3. Add a new Application Setting that corresponds with a LUIS Intent created previously
- In this demo, we created an intent called WhatIsAzure so we will enter that as the App Setting Name
- For value, we want to enter the answer to the question, in this case:
```
Microsoft Azure is an ever-expanding set of cloud services to help your organization meet your business challenges. It’s the freedom to build, manage, and deploy applications on a massive, global network using your favorite tools and frameworks.
```

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/new-answer.png)

4. Click Save at the top
5. Repeat steps 3-4 for as many Intents that were added in LUIS
