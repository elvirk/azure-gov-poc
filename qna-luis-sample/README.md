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

## Configure Bot Framework App
1. 
