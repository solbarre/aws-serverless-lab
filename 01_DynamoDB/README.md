# Amazon DynamoDB

In this module you will create, configure, and insert record to DynamoDB table.

## Implementation Instructions
Each of the following sections provide an implementation overview and detailed, step-by-step instructions. The overview should provide enough context for you to complete the implementation if you're already familiar with the AWS Management Console or you want to explore the services yourself without following a walkthrough.

### 1. Login to AWS Console section initile pour le lab
1. Go to your AWS Console
2. Login as IAM user which have enough privilege
3. Select AWS region: **N.Virginia**

### 2. Create an Amazon DynamoDB Table en mode cli

1. Depuis un serveur ou est installé aws cli 

2. Creation table dynamoDb avec cli cf doc aws   https://docs.aws.amazon.com/cli/latest/reference/dynamodb/

3. For **Table name**, type `SuperMission` ou a adapter 

4. For **Primary Key**, type `SuperHero`

5. You will see a status that "Table is being created".

8. Once the table creation process is complete, go to **Overview** tab, in **Table details** make a note of your DynamoDB table's **ARN**
 - for example: arn:aws:dynamodb:us-east-1:999999999999:table/SuperMission

### 3. Insert Amazon DynamoDB Records

- En mode cli ajouter les item en type string uniquement

- Adapter le code ci dessous

```
{
  "SuperHero": "Superman",
  "Villains": ["Doomsday", "General Zod","Lex Luthor"],
  "MissionStatus": "In progress",
  "SecretIdentity": "Clark Kent"
}
```

- Paste the code into the editor

- Click **Save**

- Repeat the above steps with below items


```
{
  "SuperHero": "Batman",
  "Villains": ["Joker", "Bane","Ras Al Ghul"],
  "MissionStatus": "Complete",
  "SecretIdentity": "Bruce Wayne"
}
```

```
{
  "SuperHero": "Iron Man",
  "Villains": ["Apocalypse", "Doctor Doom","Loki"],
  "MissionStatus": "In Progress",
  "SecretIdentity": "Tony Stark"
}
```






