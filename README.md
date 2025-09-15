# AWSWorkshop.io Base Workshop

This is a base workshop. Clone and start from this repo to create your workshop.

## Versions

* 2.0
  * Initial Release:  
      Overhauled to add prescriptive guidance. Improved readability and ease of use by making the base more templatized.

## Description

This is the base repo for building workshops with AWS. It utilizes the Hugo framework, which involves simple markdown and HTML elements.

In this workshop, you are going to learn how to plan, build, and launch an AWS workshop.

## What is a workshop?

An AWS workshop is a tool used to educate users and end customers on how to leverage partner solutions on their AWS workload. What better way to learn than to let customers get hands-on with building or instrumenting products or services in an actual AWS environment?  

A workshop format is used because it scales well, meaning you can deliver the content and message whenever and wherever the customer happens to be. Whether the customer is at work, home, or at an AWS event, they can get hands-on and learn about building products and solutions.

## High-Level Planning

While creating your workshop, you will want to think about what you want to accomplish and how you want to educate users about your product. Depending on your needs, you will either build a new workshop or use an existing one and modify it as you see fit.

You will want to create a high-level plan for your workshop and determine the problem you are looking to solve. Identifying key concepts that you want the customers to learn about is also ideal. Then, outlining what components and AWS services you are going to utilize is a key step.  

This will play a big role in creating the workflow that your customers will be following along with during the workshop. The workflow should be presented as a story and have an introduction, an educational body, and a conclusion that ties all the pieces together. A cleanup section will follow suit so that the customers can ensure their environments will not be charged after they finish the workshop.  

Determining what kind of event this workshop will be presented at is also important as it will help you have a way to capture leads, which should be the end goal in mind. (More details are covered in the workshop itself.)

## Types of Events
 
Identifying whether your workshop will be a self-paced workshop or an AWS-hosted event will be crucial in your planning as well. If it's a self-paced workshop, then having highly contextualized sections will be very important as there won't be anyone there to answer questions.  

Making sure that the workshop itself has all relevant information or that clear references have been outlined for any documentation that will be needed to successfully complete the workshop is crucial to the workshop's overall success.

## Build

In this section, you will be setting up your workflow, editing and building, testing your environments, and publishing the workshop if everything is prescriptive enough. Follow along to learn how to complete all of these tasks.

## Viewing the Workshop Locally

To view and test your workshop locally before publishing, you'll need to set up your development environment. This allows you to preview changes in real time and ensure everything works as expected.

### Development Setup Guide

Follow these steps to set up your local development environment:

1. **Install GitHub CLI (if not already installed)**

   The GitHub CLI (`gh`) makes it easy to fork and clone repositories. Install it from:

   **macOS (using Homebrew):**

   ```bash
   brew install gh
   ```

   **Windows (using Chocolatey):**

   ```bash
   choco install gh
   ```

   **Linux (Ubuntu/Debian):**

   ```bash
   sudo apt install gh
   ```

   For other installation methods, visit: https://cli.github.com/

2. **Authenticate with GitHub**

   Check if you're already authenticated, or log in if needed:

   ```bash
   gh auth status || gh auth login
   ```

3. **Fork and Clone the Repository**

   Fork this repository to your GitHub account and clone it locally:
  ```bash
  gh repo fork aws-samples/[repository-name] --clone=true
  cd [repository-name]
  ```

   Replace [repository-name]
   with the actual name of the workshop repository you want to work with.

   This command will:
   - Create a fork of the repository in your GitHub account
   - Clone your fork to your local machine
   - Set up the necessary git remotes (origin pointing to your fork, upstream to the original)

4. **Initialize and Update Git Submodules**  
   The workshop uses Hugo themes as submodules. Initialize and update them with:

   ```bash
   git submodule init
   git submodule update
   ```

   If you encounter issues where themes or submodules are not loading correctly, try running the following command to ensure everything is fully updated:

   ```bash
   git submodule update --recursive --remote
   ```

   This command ensures all nested submodules are updated to their latest versions.

   If you accidentally cloned the repository without initializing submodules, you can run the following to initialize and update them in one step:

   ```bash
   git submodule update --init --recursive
   ```

### Troubleshooting Submodules

If submodules fail to initialize or update, try these steps:

1. **Verify submodule configuration**  
   Run the following command to list all submodules and check if they are correctly set up:

   ```bash
   git config --file .gitmodules --list
   ```

2. **Remove and re-add submodules**  
   If submodules are still not working, remove and re-add them:

   ```bash
   git submodule deinit -f .
   rm -rf .git/modules/
   git submodule update --init --recursive
   ```

3. **Check for missing submodules in `.gitmodules`**  
   If errors persist, open the `.gitmodules` file and verify that the submodules are correctly referenced.

4. **Ensure correct repository permissions**  
   If your submodules are private, make sure you have the correct SSH or HTTPS access to pull them.

By following these steps, you can resolve most common submodule issues and ensure that your workshop is correctly set up for local development.

### Setup the Local Hugo Server  

5. **Install Hugo (if not already installed)**

   Hugo is a static site generator that powers this workshop. Install it using your preferred method:
   
   **macOS (using Homebrew):**
   ```bash
   brew install hugo
   ```
   
   **Windows (using Chocolatey):**
   ```bash
   choco install hugo-extended
   ```
   
   **Windows (using Scoop):**
   ```bash
   scoop install hugo-extended
   ```
   
   **Linux (Ubuntu/Debian):**
   ```bash
   sudo apt install hugo
   ```
   
   **Linux (using Snap):**
   ```bash
   sudo snap install hugo
   ```
   
   **Using Go (cross-platform):**
   ```bash
   go install github.com/gohugoio/hugo@latest
   ```
   
   For other installation methods or the latest version, visit: https://gohugo.io/installation/
   
   **Verify Installation:**
   ```bash
   hugo version
   ```

6. **Launch the Local Development Server**

   Navigate to the root directory of your cloned repository and start the Hugo development server:

   ```bash
   hugo server -D
   ```

   This will start a local server at `http://localhost:1313/`, where you can view your workshop in real time. The `-D` flag ensures draft content is also displayed.

### Working with Workshop Content

When making changes to your workshop content, the local server will automatically refresh to show your updates. This allows you to:

* See how your markdown renders in the browser
* Test navigation between pages
* Verify that images and links work correctly
* Check responsive design on different screen sizes

If you encounter issues with the local preview:

* Ensure all submodules are properly initialized
* Try restarting the Hugo server
* Clear your browser cache if changes aren't appearing

Remember that any changes made locally will need to be committed and pushed to the repository to be reflected in the published version of your workshop.

## Launch

With your workshop now being published, you can now identify some key go-to-market activities. 

## FAQ

Commonly asked questions along with tools, tips, and samples that might be relevant to your workshop. Modify this FAQ section as you best see fit for your specific workshop and your customer base. 

## Authors

Contributors' names and contact info:

* Patrick Vassell (@Vassell, Patrick)
* James Bland (@jamesbland123)
* Eugene Mu (@eugenemu)

## License

This project is licensed. See the LICENSE.md file for details.

## Acknowledgments

* [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Learn Theme Markdown](https://learn.netlify.app/en/cont/markdown/)
* [Menu Extras and Shortcuts](https://learn.netlify.app/en/cont/menushortcuts/) 
* [Using Font Awesome Emoji's to Help Your Page Pop](https://learn.netlify.app/en/cont/icons/)
