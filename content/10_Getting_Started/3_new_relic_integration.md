+++
title = "Connect AWS to New Relic"
date = 2019-10-03T10:54:25-07:00
weight = 3
+++

{{% notice note %}}
China regions are not supported.
{{% /notice %}}

To connect your Amazon account to New Relic Infrastructure:

1. Go to [infrastructure.newrelic.com](https://infrastructure.newrelic.com)  > **AWS**. Click on the **Lambda** service tile to get started.
1. Open another browser tab and navigate to the AWS IAM console, click **Create role**, then click **Another AWS account**.
 * For *Account ID*, use *754728514883*
 * Check the *Require external ID* box
 * For *External ID*, enter your New Relic account ID.
 * **Do not** enable the setting to *Require MFA* (multi-factor authentication).
1. Attach the **Policy:** Search for *ReadOnlyAccess*, select the checkbox for the policy named ReadOnlyAccess, then click **Next: Review**. 
1. For the **Role name**, enter *NewRelicInfrastructure-Integrations*, then click **Create role**.
1. Select the newly created role from the listed roles. On the **Role summary** page, select and copy the entire **Role ARN** (required later in this procedure).
1. Configure a **Budgets** policy: While viewing the **Role summary** for your new role, select  **Add inline policy**.
1. Create a **Custom policy**: Enter a policy name (for example, *NewRelicBudget*), add the following permission statement, and then select **Apply policy**.
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "budgets:ViewBudget"
      ],
      "Resource": "*"
    }
  ]
}
```
1. Return to the New Relic UI to enter your AWS account name and the ARN for the new role.
1. Select the Amazon Web Services to be monitored with New Relic Infrastructure integrations, then **Save**.
