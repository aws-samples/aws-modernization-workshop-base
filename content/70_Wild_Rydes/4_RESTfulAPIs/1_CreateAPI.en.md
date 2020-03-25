+++
title = "REST API"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Create a New REST API
Use the Amazon API Gateway console to create a new API named `WildRydes`.

**:white_check_mark: Step-by-step directions**

1. Go to the [Amazon API Gateway Console][api-gw-console]
1. Choose **Create API**.
1. Select **REST**, **New API** and enter `WildRydes` for the **API Name**.
1. Select `Edge optimized` from the **Endpoint Type** dropdown.
    ***Note***: Edge optimized are best for public services being accessed from the Internet. Regional endpoints are typically used for APIs that are accessed primarily from within the same AWS Region. Private APIs are for internal services inside of an Amazon VPC.
1. Choose **Create API**

    ![Create API screenshot](/images/wildrydes/create-api.png)

[api-gw-console]: https://console.aws.amazon.com/apigateway/home