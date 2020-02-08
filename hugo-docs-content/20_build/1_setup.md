+++
title = "Setup Environment"
chapter = false
weight = 1
+++

Building a workshop leverages several tools:

* Git
* Hugo
* Hugo learn theme
* CloudFormation templates

## 1. Clone Sample Repo
You will need to have a little familiarity with git, if not you might want to lookup a git tutorial.

Start by cloning the sample repo and push it to a repo on your own GitHub account.  Change the name of myCompany-Workshop :) 
```
git clone https://github.com/aws-samples/aws-modernization-workshop-sample myCompany-Workshop
```
> We use clone instead of fork as you will break this from the sample repo and change the name.  Once approved and published the repo will be called something to the effect aws-modernization-workshop-with-Company_Name

## 2. Download submodules
The repo uses git submodules so cd into the newly cloned repo:
```
git submodule init
git submodule update
```

## 3. Create and push to YOUR GitHub repo

**Create a repo in your GitHub account and follow the instructions under "Push an existing repository from the commandline"**

## 4. Install Hugo
```
macOS: `brew install hugo`

Windows: `choco install hugo -confirm`
```

{{% notice note %}}
To make the creation of web page documentation easier, we utilize a tool called Hugo.  You will write your documentation/instructions using markdown language and Hugo will create static html content that can be served via S3.  Hugo additionally applies a theme so that the site will have an AWS look and feel plus add additional features to beautify and make content stand out.

**For more information about installing and using Hugo, visit** https://gohugo.io/getting-started/installing/ 

**For more information about the learn theme used in Hugo, visit** https://learn.netlify.com/en/
{{% /notice %}}

## 5. Running Hugo
From within the root of the repo
``` 
$ hugo server
```
Using a browser go to http://localhost:1313 to view the site.  Hugo is dynamic, so as you edit the content and the page in the browser will change.  Allowing you to view in real-time what the content will look like.
