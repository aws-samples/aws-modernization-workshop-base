+++
title = "User Pool"
date = 2019-09-09T17:42:10+01:00
weight = 20
+++

### 2. Create an Amazon Cognito User Pool using AWS Amplify CLI

#### Background

The AWS Amplify Authentication module provides Authentication APIs and building blocks for developers who want to create user authentication experiences.

Amazon Cognito User Pools is a full-featured user directory service to handle user registration, authentication, and account recovery. Amazon Cognito Federated Identities on the other hand, is a way to authorize your users to use AWS services.

Amplify interfaces with User Pools to store your user information, including federation with other OpenID providers like Facebook & Google, and it leverages Federated Identities to manage user access to AWS Resources, for example allowing a user to upload a file to an S3 bucket. The Amplify CLI automates the access control policies for these AWS resources as well as provides fine grained access controls via GraphQL for protecting data in your APIs.

Use the Amplify CLI to create a new Cognito User Pool using the default settings.  Once your User Pool is created and associated to the web application, you'll use the Amazon Cognito Console to manage the new User Pool.

#### Amazon Cognito

**:white_check_mark: Step-by-step directions**

1. Execute the following commands to add the Amazon Cognito User Pool:
```
amplify add auth
 ```
The AWS Amplify CLI will now run through the set up for Amazon Cognito, select the folowing:

        > Do you want to use the default authentication and security configuration? "Default configuration"
        > How do you want users to be able to sign in? "Username"
        > Do you want to configure advanced settings? "No, I am done."

    Once the configuration has completed you will see the  following confirmation:
    ![Amplify auth add screenshot](/images/wildrydes/amplify-auth-add.png)

    Next you will build all your local amplify backend resources and provision it in the cloud by committing your code updates and kicking off a new build.

1. Commit the changes to your git repository:
 
``` 
git add .

git commit -m "configure cognito"

git push

```
Amplify Console should pick up the changes and begin building and deploying your web application.