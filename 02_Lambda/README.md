# AWS Lambda

In this module you will create Lambda function to process your backend logic.

![Serverless Backend Architecture](../images/serverless-backend-architecture.png)

## Implementation Instructions
Each of the following sections provide an implementation overview and detailed, step-by-step instructions. The overview should provide enough context for you to complete the implementation if you're already familiar with the AWS Management Console or you want to explore the services yourself without following a walkthrough.


### 2. On utilisera le role IAM fournis en cours
Use the IAM role. 
The role grant your function permissions to write to Amazon CloudWatch Logs and put items to your DynamoDB table.


### 3. Create Lambda Function - GetHeroesList (nompersonalisé)     avec cli

1. nodejs16.x for the Runtime.

1. Ajout du code suivant préco aws [getHeroesList.js](getHeroesList.js) into the code entry area.

1. Leave the default of `index.handler` for the **Handler** field.

1. For **Role**, click **Choose an existing role**

1. Select `lambda-supermission-role` from the **Existing Role dropdown**.

1. In the Advanced Settings section, all values canbe left at their defaults.

1. Choose **Next** and then choose **Create function** on the Review page.

1. From the **Actions** menu in the Lambda console, click **Configure test event**

1. For **Sample event template** click **Hello World**

1. Click **Save and Test**

1. You will see a message telling you that **Execution Result: Succeeded.** You will see a text box displaying contents of the SuperMission DynamoDB table.


### 4. Create Lambda Function - GetMissionDetails  (nompersonalisé)     avec cli

1. Click **Function** at left side menu

1. Click **Create a Lambda Function**

1. Choose the **Blank Function** blueprint card.

1. Don't add any triggers at this time. Choose **Next** to proceed to defining your function.

1. Enter `GetMissionDetails` in the Name field.

1. Optionally enter a **description**.

1. Select **Node.js 6.10** for the Runtime.

1. Copy and paste the code from [getMissionDetails.js](getMissionDetails.js) into the code entry area.

1. Leave the default of `index.handler` for the **Handler** field.

1. For **Role**, click **Choose an existing role**

1. Select `lambda-supermission-role` from the **Existing Role dropdown**.

1. In the Advanced Settings section, all values canbe left at their defaults.

1. Choose **Next** and then choose **Create function** on the Review page.

1. From the **Actions** menu in the Lambda console, click **Configure test event**

1. For **Sample event template** click **Hello World**

1. In the editor, remove all of the placeholder code

1. Copy the code below, and paste it into the editor. This code will look for details of Batman's mission in the DynamoDB table.   
```
{"superhero": "Batman"}
```

18. You will see a message telling you that **Execution Result: Succeeded.** You will see a text box displaying mission details for Batman.
