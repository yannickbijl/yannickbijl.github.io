---
layout: post
date: 2023-04-15 00:00:00 +0100
tags: Soft-Skills
categories: Software-Development Tools
title: 'Essentials for each Repository'
---

Version control is one of the great skills that a software developer should have. Though there is a lot to learn, the basics are readily available on the internet to learn. Commands are well documented and there are multiple software options for version control readily available.

Another important part of version control is the structure and information provided with whatever you version control. The repository structure makes your work easily navigable. Basically it comes down to working in pure chaos is difficult, thus structure your work to make it easier. The structure you want will depend mostly on your work. As an example, Python code files will be structured differently from Java code files.

A second part would then be keeping the structure clean. This will partly be a manual process, but it is possible to prevent unnecessary clutter into your repository. A gitignore file (`.gitignore`) will prevent files and directories from being committed in the repository. The webtool [gitignore.io](https://www.toptal.com/developers/gitignore) helps in creating a .gitignore file for most programming languages to keep unnecessary files out of your repository.

```bash
# python compiled code
*.pyc
# rubygem
*.gem
# VScode directory with specific settings
.vscode/
```

Besides the structure, there are two files that are important for a repository. These are the README and the the license. The README is the introduction for your repository, the poster-child if you will. Sites such as [GitHub](https://github.com/) uses the README as the default file to display. Thus the README is a great place for some basic explanation about your project and how to use it. A good place to start writing a README is [readme.so](https://readme.so/).

The license on the other hand is a file that tells others what they are allowed to do with your work. Only allowing to use the project as-is will require a different license from if you want people to freely share it. I'm not a legal advisor, so I cannot recommend one license over another. A great resource for the pros and cons of different licenses is [choosealicense](https://choosealicense.com/)
