---
title: "AWS Modernization Workshop Base Template" # MODIFY THIS TO BE THE TITLE OF YOUR WORKSHOP
chapter: true
weight: 1
---

# AWS Modernization Workshop Base Template <!-- CHANGE THIS TO BE THE TITLE OF YOUR WORKSHOP -->
### Welcome

By utilizing this template, you can create your workshops with little coding knowledge. These workshops use the Hugo Framework and the hugo-theme-learn submodules. By writing content using simple markdown code, Hugo creates the necessary HTML for you. Examples of code, files, and folders here can be modified, copied, pasted, and deleted as necessary.

### The Entry Point Of The Workshop
All modifications should be done to files in the `content` folder. `_index.md` serves as the main entry point to your workshop. Adding modules can be done utilizing the format of `#_title` as a folder within `content`. By adding a number value to the title, this helps to keep the files structured in parity with the content of the workshop. A good practice for file naming is to have the folder be the module number and the submodule numbers add to that number reflecting their order. For example, the first module is `1_ModuleOne` and the submodules would be `11_SubmoduleOne`, `12_SubmoduleTwo`, and so forth. <br> <!-- <br> applies a line break to paragraphs -->
To ensure the modules and submodules follow the correct structure order, adjust the "weight" value in the heading of the file to reflect the order you wish to use. Three module examples are included in this template with the second being split based upon the method of setup. The same rules apply for submodules. `_index.md` is the entry point of that module with submodules following the `#_title.md` format within the module folder.

### Working With Hugo Markdown and Shortcode
The following links will supply you with all the reference documentation about Hugo markdown. For more experienced developers, inline HTML is also an option to add more customization. For example `<p style='text-align: left;'>` inline will allow you to adjust your text placement.

### Markdown and Shortcode Resources
{{% notice tip %}}
The following links are your go-to resource for markdown and shortcode reference in building your workshop: <br>
* Markdown cheat sheet https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet <br>
* Learn theme markdown https://learn.netlify.app/en/cont/markdown/ <br>
* Menu extras and shortcuts https://learn.netlify.app/en/cont/menushortcuts/ <br>
* Using Font Awesome Emoji's <i class="fas fa-heart"></i> https://learn.netlify.app/en/cont/icons/ to help your page pop <i class="fas fa-glass-cheers"></i>
{{% /notice %}}

### Adding Images and Static Media
Any images and static media to be included in the workshop need to be placed in the `static/images` folder. The format to display an image is as follows: `![Alternate Text](/images/imagename.jpg)` <br>

For example, the markdown for this dog is `![An adorable puppy](/images/dog.jpg)` and the image is in the `static/images` folder. <br>
![An adorable puppy](/images/dog.jpg)

### Creating Links
The format for creating links is `[Link Display Text](http://example.com)`. For example, this link [Hugo Framework](https://gohugo.io/about/what-is-hugo/) was created using `[Hugo Framework](https://gohugo.io/about/what-is-hugo/)`.

### The "More" Menu Section
This section of the menu on the left is designed to add additional resources that are related to the workshop but not necessarily part of the workshop itself. To modify these links, edit the sections marked `[[menu.shortcuts]]` in the `config.toml` located in the root folder. The "name" portion will be what is displayed in the menu. The "url" should be the address of the link. The "weight" setting will adjust the display order, similar to the other "weight" settings utilized in indexes and modules mentioned previously.

### Ensuring Pages Appear In Both Setup Versions
A shortcut to creating the workshop with different setup versions is utilizing the localization functionality of Hugo. By adding a secondary extension to the filename, this file will be included in the specific version of the workshop. Currently, the base utilizes the format `*.ee.md` to signify that the page is to be used in the AWS EventEngine setup. Much of the time, the files will be the same as the content only differs at specific points. It is necessary to add them, however, to make sure that the common content is duplicated across both versions. If you wish to change the secondary extension or default version, this can be done in the `config.toml` file in the heading and `[Languages]` sections.