# Github
> In this chapter we will learn about Github and explore some of its many features


[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/karpatic/datalab/master?filepath=%2Fnotebooks%2F0_github.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/colab.svg)](https://colab.research.google.com/github/karpatic/datalab/blob/master/notebooks/0_github.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/github.svg)](https://github.com/karpatic/datalab/tree/master/notebooks/0_github.ipynb)
[![Open Source Love svg3](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)

[![NPM License](https://img.shields.io/npm/l/all-contributors.svg?style=flat)](https://github.com/karpatic/datalabs/blob/master/LICENSE)
[![Active](http://img.shields.io/badge/Status-Active-green.svg)](https://karpatic.github.io) 
[![Python Versions](https://img.shields.io/pypi/pyversions/dataplay.svg)](https://pypi.python.org/pypi/dataplay/)
[![GitHub last commit](https://img.shields.io/github/last-commit/karpatic/datalabs.svg?style=flat)]() 
[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/) 

[![GitHub stars](https://img.shields.io/github/stars/karpatic/datalabs.svg?style=social&label=Star)](https://github.com/karpatic/datalabs) 
[![GitHub watchers](https://img.shields.io/github/watchers/karpatic/datalabs.svg?style=social&label=Watch)](https://github.com/karpatic/datalabs) 
[![GitHub forks](https://img.shields.io/github/forks/karpatic/datalabs.svg?style=social&label=Fork)](https://github.com/karpatic/datalabs) 
[![GitHub followers](https://img.shields.io/github/followers/karpatic.svg?style=social&label=Follow)](https://github.com/karpatic/datalabs) 

[![Tweet](https://img.shields.io/twitter/url/https/github.com/karpatic/datalabs.svg?style=social)](https://twitter.com/intent/tweet?text=Check%20out%20this%20%E2%9C%A8%20colab%20by%20@bniajfi%20https://github.com/karpatic/datalabs%20%F0%9F%A4%97) 
[![Twitter Follow](https://img.shields.io/twitter/follow/bniajfi.svg?style=social)](https://twitter.com/bniajfi)

Information for this section was obtained from the Pro Git book, written by Scott Chacon and Ben Straub and published by Apress under the [Creative Commons Attribution Non Commercial Share Alike 3.0 license](https://creativecommons.org/licenses/by-nc-sa/3.0/). An [online](https://git-scm.com/book/en/v2/) version and Free [Ebook](https://github.com/progit/progit2/releases/download/2.1.228/progit.pdf") are also available

## Whats Covered

### We will cover in this lab

Version Control
- What is it?
- Why do we need it?
- How is it done?

Github
- What is it?
- Creating an account
- Creating a repository
- Commiting changes
- CLI, Desktop tools

Miscellaneous (*=not covered)
- Versioning 
- Commiting from Colab 
- Create a repo from an existing [project](https://docs.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line)

### What will be cover in later chapters
- The CLI
- Github [Pages](https://docs.github.com/en/github/working-with-github-pages) and [Jeckyll](https://docs.github.com/en/github/working-with-github-pages/adding-a-theme-to-your-github-pages-site-using-jekyll)

### What will not be covered but is noteworthy
- Browser [Extensions](https://github.com/collections/github-browser-extensions)
- Github's [special](https://torrocus.com/blog/special-github-repository/) 'profile' repository
- Github Projects - Dev/mgmt tools and Collaborative Kanbanboards all wired up to respond to git commits. 
- Github Teams - A chatroom for people working on a repository
- Github Organizations - Can house multiple repositories and provides admin tools to manage people across teams and projects. 
- Github [NPM](https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-npm-for-use-with-github-packages) - Publish Javascript libraries to NPM using Github
- Github [Actions](https://github.com/features/actions)

## Version Control

### What is it?

> Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later - Chacon and Straub, Pro Git

### Why do we need it?
> Many people’s version-control method of choice is to copy files into another directory (perhaps a time-stamped directory, if they’re clever). This approach is very common because it is so simple, but it is also incredibly error prone. It is easy to forget which directory you’re in and accidentally write to the wrong file or copy over files you don’t mean to... The next major issue that people encounter is that they need to collaborate with developers on other systems. - Chacon and Straub, Pro Git

### How is it done?

> This is where Distributed Version Control Systems (DVCSs) step in. In a DVCS (such as Git, Mercurial, Bazaar or Darcs), clients don’t just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.  - Chacon and Straub, Pro Git

## Git

__Git__ is an open source tool used by developers to establish version control in ther projects using commands executed from the terminal. 

__Github__ (covered in the next section) is a website/ application that allows you to upload your git repository to the web for distributed collaboration, control and storage. 

> Since its birth in 2005, Git has evolved and matured to be easy to use and yet retain these initial qualities. It’s amazingly fast, it’s very efficient with large projects, and it has an incredible branching system for non-linear development (See Git Branching). - Chacon and Straub, Pro Git


- Nearly Every Operation Is Local 
> Most operations in Git need only local files and resources to operate — generally no information is needed from another computer on your network.  - Chacon and Straub, Pro Git

- Git Has Integrity 
  > Everything in Git is checksummed before it is stored and is then referred to by that checksum. This means it’s impossible to change the contents of any file or directory without Git knowing about it. This functionality is built into Git at the lowest levels and is integral to its philosophy. You can’t lose information in transit or get file corruption without Git being able to detect it. - Chacon and Straub, Pro Git

- Git Generally Only Adds Data

  > When you do actions in Git, nearly all of them only add data to the Git database. It is hard to get the system to do anything that is not undoable or to make it erase data in any way. As with any VCS, you can lose or mess up changes you haven’t committed yet, but after you commit a snapshot into Git, it is very difficult to lose, especially if you regularly push your database to another repository. - Chacon and Straub, Pro Git

While there are many ways to use git, the general approach follows these three stages

<br> <img src="https://charleskarpati.com/img/githubCommit.png" alt="Git Stages" title="Git Stages" height="300"/>


Using Git accomplished through a variety of manners:

- Directly through the [command line](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line)
- Using [Github](github.com)  or [Bitbucket](https://bitbucket.org/) on the web
- Using Github's [Desktop](https://desktop.github.com/) Application (Simplified, User friendly)
- Or a variety of other third party tools like the web based [Prose.io](https://prose.io/) content editor

## Github

Wheras Git may be used stand-alone for version control purposes it is often used in tandem with Github (or Bitbucket).

Github ( a free service) enriches existing features and adds further utility, as we will see soon.

To truly understand what this means, lets try it out!

### **1: Create a Github account**

**1a. [Create](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home) a new GitHub account** <br><img src="https://charleskarpati.com/img/githubcreate.png" height="400"/>

**1b.** The top right corner provide shortcuts to some of githubs best features.

Shown below is the accounts dropdown.

**Click on the 'Your Profile' tab to be led to a dashboard comprising all your past works (if any).**

<br><img src="https://charleskarpati.com/img/githubAccountTab.png" height="400"/>

Your username will be the URL's basepath for all future projects. More on this later.

**This basepath also serves as the link to your profile page.**

If you are feeling brave, click on different tabs in this dropdown to see how they relate to your profile page and basepath!

**For Example, the link to my profile page is as follows:**
<br><img src="https://charleskarpati.com/img/githuburl.png"/>

**If I click 'Your repositories' dropdown option:**
- The url changes to github.com/karpatic?tab=repositories**
- The navigational tab on the topmost of my homepage will change from 'Overview' to 'Repositories'.
<br><img src="https://charleskarpati.com/img/githubProfileRepos.png" height="150"/>

### **2: Create a project repository**

####**2a. Navigate to the '+' Menu Button and click "New Repository"** 

**Other features in here:**
- '[New Gist](https://help.github.com/en/github/writing-on-github/creating-gists)' - **(Free)** - Save something quick!
- - Click that link or visit https://www.gist.github.com to jot something down!
- - Save the code and get back to it later from https://gist.github.com/Your_UserName 
-- Markdown, Html, and JS syntax are all understood.
- '[New Organization](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/about-organizations)' - **(Free and paid)** - BNIA has a free one. Helps people collaborate across many projects/ repos.
- '[New Project](https://github.com/features/project-management/)' - **(Free and paid)**, for project management.

<br><img src="https://charleskarpati.com/img/NewRepoPic.png" height="200"/>


#### **2b. Complete the form that appears with your information.**

- Be sure to click "Initialize this repository with a README".
- A sample is provided below.<br><br><img src="https://charleskarpati.com/img/githubCreateRepository.png" height="700"/>

**More information on setup and configuration can be found [here](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration)**

### **3: Editing a file in the repo**

#### **3a. At this point, you should be looking at something like this:** 
- **Green** (topright) - Quick links
- **Mint/Pistachio** (topleft) - Basepath / ProjectName
- **Purple** (second most topright)
- - Watch a project to track its progress with using alerts
- - Click the star to favorite a project. 
- - Fork a project to create an identical copy
- **Red** (third most topright) 
- - Delete or rename a project here. 
- - If youre code contains Markup, HTML, or JS it can be hosted for **free** using github [pages](https://pages.github.com/)
- **Light Blue** (center screen) - See when the project was last edited here.
- **Gray** (Center screen) 
- - This is the file directory. 
- - All files will be shown here. 
- - Click a link to change the page and view its contents.
- - Clicking a file from the file directory will show the content of the file much like is demonstrated in the yellow and orange section in the picture
- **Yellow** (bottom) 
- - If the project has a README.MD file, the content of that file file will be parsed, rendered, and shown here.
- **Orange** (bottom above the yellow) 
- - The filename is shown in the left orange circle.
- - commit edits to the README doc using the right circle pencil icon.
<br><img src="https://charleskarpati.com/img/githubreponew.png" height="500"/>

**The contents of a README.md file should be shown towards the bottom half of your screen.**

#### **3b**. You are now looking at the contents of the readme file. 
- - You can edit the document using HTML, Markdown or plaintext. 
- - To commit your edits, scroll to the bottom of the page, Edit 

<br> <img src="https://charleskarpati.com/img/githubCommit.png" height="500"/>

# Congratulations! 

**To learn more about [Markdown](https://guides.github.com/features/mastering-markdown/)** and other cool github features, check out their **[Guides](https://guides.github.com/)**
