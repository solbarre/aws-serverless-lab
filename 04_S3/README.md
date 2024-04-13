# Amazon S3

In this module you'll configure Amazon Simple Storage Service (S3) to host the static resources for your web application. 

![Serverless Basic Architecture](../images/complete-architecture.png)

## Implementation Instructions
Each of the following sections provide an implementation overview and detailed, step-by-step instructions. The overview should provide enough context for you to complete the implementation if you're already familiar with the AWS Management Console or you want to explore the services yourself without following a walkthrough.


### 2. Generate the SDK for your API en mode cli

1. la commande va download dans le rep courant le package SDK zippé

1. Open the directory (your Downloads folder) and extract the contents of the ZIP to your local computer

1. Next, you will retrieve an HTML page that you will use to test your API. Go to [index.html](index.html)

1. Copy the content, save it as  **index.html** to your local computer previously extracted **apiGateway-js sdk** folder

1. Open **index.html** in your browser (a adapter au besoin)

1. Using the index web page, retrieve mission details. Review the output.

### 3. Integrate with S3 Static Website

-  **Create Bucket** en cli

- creer fichier website.json pour transformer bucket en website statique et l'integrer cf doc s3 https://docs.aws.amazon.com/cli/latest/reference/s3api/
{
    "IndexDocument": {
        "Suffix": "index.html"
    }
}

5- Rendre le S3 Bucket public

Une commande s3api est a lancer pour rendre le s3 bucket public*

- **Bucket Policy**

6- Créer un fichier policy.json et attacher la policy au bucket S3

```
{   
    "Version": "2012-10-17",   
    "Statement": [   
        {   
            "Effect": "Allow",   
            "Principal": "*",   
            "Action": "s3:GetObject",   
            "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"   
        }   
    ]   
}   
```


7-publier le contenu statique du site web dans le bucket S3

copie sur le bucket avec cli s3     l'index.html aura été déplacé dans le dossier dézippé du pack SDK de l'api

- Take a note of **Endpoint** URL (ex. http://mybucket.s3-website-us-east-1.amazonaws.com)


`http://<my-unique-bucket-name>.s3-website-us-east-1.amazonaws.com`

- You can now hosting website in S3 to look up data stored in your DynamoDB database using API Gateway and Lambda function.
