+++
title = "Edit and Build"
chapter = false
weight = 10
+++

## Directory Tree
Directory of artifacts you will add, change, delete during the course of building a workshop.
```bash
  /
   |-content
   |---10_first_section
   |---20_second_section
   |---30_third_section
   |-modules
   |-samples
   |---cloudformation
   |---codebuild
   |-static
   |---images
   |config.toml
 
```

## Editing 
Hugo uses markdown to generate static html pages.  This makes it easier to create a web based workshop as all you need to do is create documents using markdown and Hugo will create the pretty html for you.  For additional information on markdown, visit the learn theme documentation page https://learn.netlify.com/en/cont/markdown/

#### config.toml file
Start by editing the config.toml file. Only the Title needs to be edited at this time.
```bash
baseURL = "/"
languageCode = "en-US"
defaultContentLanguage = "en"

title = "AWS Modernization Workshop Sample"
theme = "hugo-theme-learn"
metaDataFormat = "yaml"
defaultContentLanguageInSubdir= true
```
#### Start Hugo Server
```bash
hugo server
```
> Navigate to localhost:1313 in your browser to see the sample site

#### Content editing
Now lets start editing content. Hugo uses the content stored in `content` to build web pages.  If you look under the directory there is a file _index.md.  This is the starting point of the documentation and is the equivalent of index.html.  Each folder becomes the high level navigation.  Each of the folders and files are prefixed with a number, which is there for visual ordering only and does not have an effect on the actual html or workshop order.  You will want to look at each and every file in the content directory tree and edit.

Start with `/content/_index.md` 
Each of the files has what Hugo calls front matter.  This is basically metadata that Hugo uses when generating the files.  Here is an example, note the Title and weight fields.  Weight controls the ordering, lower number the higher the order.

```bash
---
title: "Main Page"
chapter: true
weight: 1
---
```

**Edit** The title and the text below the 3 dashes, now **Save** If everything went well the browser should refresh with the changes you have just make.

#### Edit folder names and files
The folder names are stubs and should be edited to make clear what type of content is stored in them.  The file `_index.md` within each folder sets the order using the weight front matter, and the name that appears in the left navigation pane.  Once again names are prefixed with a number only to visually sort, the `weight` is what really determines the ordering.

{{% notice tip %}}
When creating additional sections or pages, just copy the files from another section, rename and edit.  
{{% /notice %}}

#### CloudFormation and CodeBuild samples
In the workshop sample there is a sample directory with examples of CloudFormation Templates and CodeBuild buildspec.yml files.  Feel free to leverage these samples in your solution.  **Note** this is a workshop so samples are not meant to be best practice, but more for educational purposes only.  So if your workshop uses an RDS instance there is no reason to setup replication, backups, and everything else that goes along with making a robust solution, this is of course unless your workshop is on building robust fault tolerant solutions :)

#### Scripts, Artifacts, custom CloudFormation templates
If your workshop includes custom scripts, artifacts, etc... you should save them to the content folder where they will be needed.  As an example, if I have a getting_started.sh that is used in the First Section, I would place that script in `content/10_first_section`

#### Special markdown samples
See content/10_first_section/1_page.md for examples of short codes and special template code to help your workshop pop.

#### Additional editing tips 

* Use Cloud9 for the IDE and workshop host for all participants.  Having users setup their local workstations doesn't work very well and often contributes to a poor user experience.
* Review the flow of other workshops. 
* To create a new page, copy another document and rename it.  The name is only important to the builders, but the actual name that shows in the navigation is the title at the top of the document.  
* If you want to create a new page between 10 and 20 you can use any number in the name as long as it's sequentially between 10 and 20.  Don't forget to appropriately set the weight in the top section.
* Place all images in {repo_root}/static/images.  There are several examples of using images in the sample content.
* Provide users with sample output in `<pre> </pre>` tags so that the copy to clipboard function is not there.  No reason to copy example output to the clipboard.
* DO NOT assume that the user has any exposure to AWS or your product.  Everything needs to be explained and all command or areas in the UI you want the user to go to needs to be provided.  Screen shots or examples work well for this, especially on busy UI's.  
* Use an architecture diagram in your workshop.  Show people what are going to deploy.  Visuals work wonders when educating people about abstract concepts.  


