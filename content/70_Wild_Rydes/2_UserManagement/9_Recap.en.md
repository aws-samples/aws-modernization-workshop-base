+++
title = "Recap"
date = 2019-09-09T17:42:10+01:00
weight = 99
+++

### :star: Recap

:key: Amazon Cognito provides two different capabilities for managing users, federated identities and user pools. [Amazon Cognito][cognito] user pools can handle almost every aspect about managing users, their login credentials, handling password resets, multifactor authentication and much more!

:wrench: In this module you've used user pools to create a completely hosted and managed user management system that will allow us to authenticate your users and manage their user information. From there you've updated the website to use the user pool and utlized the AWS SDKs to provide a signin form on the site.

### Next

:white_check_mark: After you have successfully logged into your web application, you can proceed to the next module, [Serverless Backend][serverless-backend].

### Extra

* Try copying the **auth_token** you've received and paste that into an [online JWT Decoder][jwt-decoder] to understand what this token means for your application

[cognito]: https://aws.amazon.com/cognito/
[jwt-decoder]: https://jwt.io/
[serverless-backend]: ../3_serverlessbackend.html
