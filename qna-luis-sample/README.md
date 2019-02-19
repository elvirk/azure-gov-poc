# QnA/LUIS Sample
## Create Resource in Azure Gov
1. Create Resource Group

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20rg.jpg)

2. Create LUIS Instance

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20luis.jpg)

3. Create Bot Framework App

![](https://raw.githubusercontent.com/jimstrang/azure-gov-poc/master/qna-luis-sample/images/create%20web%20app%20bot.jpg)

## Configure LUIS
1. Login to the LUIS applications portal (https://luis.azure.us/applications)
2. Open up the LUIS application that was created during the bot framework app deployment
3. Click "Create New Intent"
- Name the intent after the question you want answered
- This should be a unique "key value" that you can reference to tie to a response later
4. After creating a new Intent, add different Utterances that are derivatives of the question you want
- For example, you might type in "What is Azure?", "Azure basics", "Tell me about Azure", etc.
- This helps train the model to direct different questions to the appropriate single response

