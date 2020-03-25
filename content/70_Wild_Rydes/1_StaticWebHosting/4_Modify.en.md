+++
title = "Modify"
date = 2019-09-09T17:42:10+01:00
weight = 40
+++

### 4. Modify the website
The AWS Amplify Console will rebuild and redeploy the app when it detects changes to the connected repository. Make a change to the main page to test out this process.

**:white_check_mark: Step-by-step directions**

1. From your Cloud9 environment open the ```index.html``` file in the `/wild-rydes/public/` directory of the repository.
1. Modify the title line:
    ```
      <title>wildrydes</title>
    ```
    So that it says:
    ```
      <title>Wild Rydes - Rydes of the Future!</title>
    ```
    Save the file
1. Commit again to your git repository the changes:
    ```
    git add . 

    git commit -m "updated title"
    
    git push
   ```
    Amplify Console will begin to build the site again soon after it notices the update to the repository. It will happen pretty quickly! Head back to the [Amplify Console][amplify-console] to watch the process. 

1. Once completed, re-open the Wild Rydes site and notice the title change.
    
    ![title updated](/images/wildrydes/title-update.png)

[amplify-console]: https://console.aws.amazon.com/amplify/home
