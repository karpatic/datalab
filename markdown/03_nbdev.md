# Nbdev
> In this chapter we learn about publishing python notebooks with nbdev. 


```
! nbdev_upgrade
```

    /bin/bash: nbdev_upgrade: command not found


## (Non-Technical) Introduction

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/karpatic/datalab/master?filepath=%2Fnotebooks%2F03_nbdev.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/colab.svg)](https://colab.research.google.com/github/karpatic/datalab/blob/master/notebooks/03_nbdev.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/github.svg)](https://github.com/karpatic/datalab/tree/master/notebooks/03_nbdev.ipynb)
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

Fastai, the org that created this tool, helps empower others by lowering the barrier of entry when breaking into software (AI) development. 

In their own words:

> Nbdev is a tool that allows you to fully develop a library in Jupyter Notebooks, putting all your code, tests and documentation in one place. -[Nbdev](http://nbdev.fast.ai/)

Some (not all) of the tools **fastai provides**:

- [Nbdev](https://github.com/fastai/nbdev) - For software development and documentation
- [Fastpages](https://github.com/fastai/fastpages) - Works like Nbdev but for blogging
- [Fastscript](https://github.com/fastai/fastscript) - Convert a python function to a CLI script
- [Fastprogress](https://github.com/fastai/fastprogress) - Reveals a progress bar for long processes
- [FastiAi](https://github.com/fastai/fastai) - Data convenience tools and AI models
- [FastAi Course](https://course.fast.ai/) - V3. A practical deep-learning course

Use one of these products? Tweet @jeremyphoward and [staff](https://www.fast.ai/about/#founders) or @HamelHusain for all their work!

### With Nbdev you can:

*Specifics covered later*

1) **Publish notebooks** as a module on pypi 
- A) "Flag" cells to [export](http://nbdev.fast.ai/export/) them as part of the python library

2) **Install it anywhere**: `pip install <nameOfModule>`
- A) This can be used in conjunction with Fastscript to create CLI scripts
- B) The CLI help interface is reachble by typing `! <NameofMdule> -h`

3) **Convert notebooks to documenation** in html and markdown 
- A) Use the index.ipynb to auto-generate a homepage
- B) Use the index.ipynb to auto-generate a Github and PyPi README.md file
- C) Have backticked function auto link to a functions github sourcecode
- D) Host the documentation on github pages so they are always up to date
- E) "Flag" cells to collapse or hide the cells (or the output) from the documentation
- F) Personalize the [Jekyll](https://jekyllrb.com/) website templates used to make the site
- G) Store photos in an images folder for use in your notebook and have it copied to your website

4) **Use created modules across notebooks in realtime**
- A) Auto-reload modules across notebooks during development if any part of the module is updated 

### Fun Facts


The Nbdev library and tutorial is actually written using a notebook.

The Nbdev library and tutorial get created and published by running the notebook on itself!

If you check, you'd see that their [tutorial](http://nbdev.fast.ai/) is actually being hosted on [github](https://github.com/fastai/nbdev/tree/master/docs) pages.

### *Real quick!*

If this is more than you need, consider 

- Sharing the Colab links directly. 
- [Nbconvert](https://nbconvert.readthedocs.io/en/latest/) notes into HTML, LaTeX, PDF, Markdown, ..
- Using [mybinder](https://mybinder.org/)
> Have a repository full of Jupyter notebooks? With Binder, open those notebooks in an executable environment, making your code immediately reproducible by anyone, anywhere.

*Okay, please continue*

## (Technical) Overview

1. Nbdev is a python library that is executed directly from the terminal.

2. At its heart, a user simply enters a directory and executes one of the nbdev terminal commands.

3. Python Notebooks will automatically be located and processed for publication and deployment.

4. Nbdev specific "Flags" (Either the Comment or ["Magic"](https://ipython.readthedocs.io/en/stable/interactive/magics.html#) variety ) tell nbdev how to treat cells

5. Photos stored in the 'images' folder will be copied over to your publication folder


### <a name="nbcmd"></a>Nbdev Terminal Commands

Entering these commands in to the terminal at the projects root directory will handle most everything. 

*Pip and Git specific steps not listed but are included in sections below.*

{% include important.html content='Information in this section is incomplete! Quotes found here-in came from Nbdev&#8217;s [official documentation](https://nbdev.fast.ai/cli/#nbdev_nb2md) from which you will derive much more insight with respect to using these functions.' %}

#### Create

> - `nbdev_new` creates a new nbdev project
> - `nbdev_update_lib` propagates any change in the library back to the notebooks

#### Compile

> - `nbdev_nb2md` converts a notebook to a markdown file
> - `nbdev_build_docs` builds the documentation from the notebooks
> - `nbdev_build_lib` builds the library from the notebooks
> - `nbdev_bump_version`/ `nbdev_bump` increments version in settings.py by one

*nbdev ignores any file that starts with an underscore*

*Version Bumping must be performed each time prior to uploading to pypi*

Combine commands with with regular expressions for more power!
- A commands like `nbdev_build_docs --fname=[!test]*.ipynb` will run all files except ones with filenames that start with 'test'

#### Publish


> - `nbdev_clean_nbs` removes all superfluous metadata form the notebooks, to avoid merge conflicts
> - `nbdev_install_git_hooks` installs the git hooks that use ( `nbdev_fix_merge` and `nbdev_diff_nbs`) automatically on each commit/merge.

*Githooks needs to be ran once on project creation for them to be set up perminantly*

#### Check

> - `nbdev_read_nbs` reads all notebooks to make sure none are broken
> - `nbdev_trust_nbs` trusts all notebooks (so that the HTML content is shown)
> - `nbdev_upgrade` updates an existing nbdev project to use the latest features

nbdev_upgrade can be run any time there are new updates. It only needs to be ran once per update.

%nbdev_collapse_input close
### <a name="nbflags"></a> Nbdev Flags (Mark Up/ Cell Magic) 

Whereas Nbdev's terminal commands should be executed at a projects root directory...

Content covered in this section need to be placed in the cells of other notebooks in the directory. 

Nbdev scripts rely on special [comments **or** magics](https://nbdev.fast.ai/tutorial/#nbdev-flags) (your choice) for cell-level handling of notebooks.

{% include important.html content='The list shown below was obtained from [here](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/06/02/nbdev-magic.html). As always, please refer to the official source for up to date information.' %}

| Comment flag                           | Magic flag                  |                                                                                |
|----------------------------------------|-----------------------------|--------------------------------------------------------------------------------|
| `default_exp`                          | `nbdev_default_export`      | Define the name of the module everything should be exported in                 |
| `exports`                              | `nbdev_export_and_show`     | Export and show code in the docs                                               |
| `exporti`                              | `nbdev_export_internal`     | Export but don’t show in docs and don’t add to `__all__`                       |
| `export`                               | `nbdev_export`              | Export but don’t show in docs                                                  |
| `hide_input`                           | `nbdev_hide_input`          | Do not show input of a test cell in docs                                       |
| `hide_output`                          | `nbdev_hide_output`         | Do not show output of a test cell in docs                                      |
| `hide`                                 | `nbdev_hide`                | Do not show a test cell or markdown in docs                                    |
| `default_cls_lvl`                      | `nbdev_default_class_level` | Define the default toc level of classes                                        |
| `collapse_output` or `collapse-output` | `nbdev_collapse_output`     | Inlcude output in the docs under a collapsable element                         |
| `collapse_show` or `collapse-show`     | `nbdev_collapse_input open` | Inlcude input in the docs under a collapsable element that is open by default |
| `collapse_hide` or `collapse-hide`     | `nbdev_collapse_input`      | Inlcude input in the docs under a collapsable element                         |
| `collapse`                             | `nbdev_collapse_input`      | Inlcude input in the docs under a collapsable element                         |

{% include warning.html content='[nbdev_upgrade](https://nbdev.fast.ai/cli/#nbdev_upgrade) need to be ran/set up before **everything** will work properly. Enabling the #collapsable flag to work on html markup sections. This [article](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/06/02/nbdev-magic.html) covers exactly how to do that. ' %}

The cell `#default_exp core` cell found at the top of the `00_core.ipynb` template, defines the name of the generated module (lib_name/core.py). 

Text-cells ignore all but `#hide` flags, use it for "developer-only" markdown notes that are hidden from HTML docs.

Comments will show in the docs if the special comment is not the 1st thing in the cell. 

To gain access to [Nbdev's new 'magics'](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/06/02/nbdev-magic.html) you my find it neccesary to:
1. Execute the command `nbdev_upgrade`, only once, and then..
2. Add `from nbdev import *` to the top of a notebook in a code-cell.

**0**. **Automated Documentation** :

Functions and Classes have are automatically documented. 

Class methods are not shown by default, though, so use [`show_doc(class.method`)](http://nbdev.fast.ai/showdoc/#show_doc) to do this.

**1**: **Automated Document Hyperlinking** : 

Nbdev will hyperlink any text cell with a backticked function name to it's sourcode on github (only if its an exported function).

**2**: **Autoreloading** : (I have note tried)
> Since you'll be often updating your modules from one notebook, and using them in another, it's helpful if your notebook automatically reads in the new modules as soon as the python file changes. 


First run this in the notebook you want to update:`notebook2script()`

Then this to the top of your notebook as a code cell:

```
%load_ext autoreload
%autoreload 2
```



### Other Magic Markups and Flags

{% include warning.html content='Content in this section is pulled from the Fastpages [blog](https://fastpages.fast.ai/fastpages/jupyter/2020/02/21/introducing-fastpages.html#Other-Feautures) [posts](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/07/24/nbdev-deep-dive.html) and the Nbdev docs. If you have any issues, you will have to scoure these sources to resolve them!' %}

**1. Anchor Links**
> An anchor link is a web link that allows users to leapfrog to a specific point on a website page. It saves them the need to scroll and skim read – and makes navigation easier. - [Telegraph](https://www.telegraph.co.uk/branded-content/marketing-guides/what-is-anchor-link/)
Example:
<a name="hyperlinkingValue"></a> Both landmark and [hyperlink ](#hyperlinkingValue) have been placed on this line. Click the link for this line to zip up to the top of your screen. 

Code: 
``` 
# This is the hyperlink
[hyperlinktext](#hyperlinkingValue) 

# It will take you to wherever you place this landmark
<a name="hyperlinkingValue"></a>
```



**2. An 'images' folder** can be used to conjure up pictures like so:

`![](images/company_logo.png)`

These images will be added to added and displayed in the docs

**3. Jekyll [Notes](http://nbdev.fast.ai/export2html/#add_jekyll_notes)**

The following section was written using the following markups 

```> Note:```, ```> Warning:```, ```> Tip:``` and ```> Important: text goes here```
{% include note.html content='This is a note.' %}{% include warning.html content='This is a warning' %}{% include tip.html content='This is a tip' %}{% include important.html content='This is an Important doc link to [`add_jekyll_notes`](/export2html#add_jekyll_notes) which should also work fine' %}

### Misc Nbdev Percs

**0. [Search](http://nbdev.fast.ai/search/)** functionality is not covered here, but may be added.

**1. Custom Sidebar**'s for your HTML documentation can be configured using meta-markup, [JSON](https://www.json.org/json-en.html).
> The default sidebar lists all html pages with their respective title, except the index that is named "Overview". To build a custom sidebar, set the flag custom_sidebar in your settings.ini to True then change the sidebar.json file in the doc_folder to your liking. Otherwise, the sidebar is updated at each doc build.

**2. [YAML](https://yaml.org/)**, a data-serialization standard, is used as [Front Matter](https://assemble.io/docs/YAML-front-matter.html) that can be [used with Jekyll](https://jekyllrb.com/docs/datafiles/) to render templates.> In the markdown cell with the title, you can add the summary as a block quote (just put an empty block quote for an empty summary) and a list with any additional metadata you would like to add **[`get_metadata`](https://nbdev.fast.ai/export2html/#get_metadata)**
**3. Console Scripts** are made by marking up functions using the [fastscript](https://fastscript.fast.ai/) tool and editing the settings.ini file ([example](https://github.com/fastai/nbdev/blob/554e63b1b05390a3ad2bc086d8485f98b1e63ca4/settings.ini) )


## Getting Started ( Run Every Time )

To get started, install the nbdev libarary.

```
%%capture
! pip install nbdev
```

### Connect to Folder

Give Colabs access to your google drive

```
#hide_output
from google.colab import drive
drive.mount('/content/drive')
```

Then navigate to the drive directory where you store your projects folder.

```
%%capture
cd drive/'My Drive'/
```

```
cd 
```

## Creating a New Project

The nbdev library will only work in projects that have the proper file structure and files. 

Once configured, you may simple write in a notebook (placing Nbdev 'FLAGS' where needed) and publish using an Nbdev terminal commands. The Nbdev command will process the notebook and each of its cells according to rules denoted by the 'FLAGS'.

### Getting a template

You can grab a free project template (containing all the needed files and proper structure) to get you started in one of two methods shown below.

#### Method 1) Grabbing a template using github and the browser

Now create a new [repository](https://github.com/fastai/nbdev_template/generate)

```
%nbdev_hide_output
! git clone https://github.com/karpatic/thisisatemplate.git
```

#### Method 2) Grabbing a template using the Nbdev library and the terminal

An Nbdev terminal command can be used to **create a template** project directory.

Use -h to view positional args.

```
! nbdev_new -h
```

    usage: nbdev_new [-h] [--template_git_repo TEMPLATE_GIT_REPO] [--xtra XTRA]
                     name
    
    Create a new nbdev project with a given name.
    
    positional arguments:
      name                  A directory to create the project in
    
    optional arguments:
      -h, --help            show this help message and exit
      --template_git_repo TEMPLATE_GIT_REPO
                            url to template repo (default:
                            https://github.com/fastai/nbdev_template.git)
      --xtra XTRA           Parse for additional args


We will need to **register your github credentials** appropraitely configured for it to work.

```
! git config --global user.email "charles.karpati@gmail.com"
! git config --global user.name "karpatic"
```

And now you can just **run the command to create a new project**/ (and directory) by a name of your choosing.

```
%nbdev_hide_output
! nbdev_new 'test123'
```

If you enter into it, you'll see it comes all set up.

As you can see it comes all set up.

### Configuring the template

**There are some one off's to perform on the template.**

#### Githooks

Run `! nbdev_install_git_hooks` 
> To set up git hooks which will remove metadata from your notebooks when you commit, greatly reducing the chance you have a conflict. 
> 
> But if you do get a conflict later, simply run nbdev_fix_merge filename.ipynb. This will replace any conflicts in cell outputs with your version, and if there are conflicts in input cells, then both cells will be included in the merged file, along with standard conflict markers (e.g. =====). Then you can open the notebook in Jupyter and choose which version to keep.
 ~ nbdev [tutorial](http://nbdev.fast.ai/cli/#nbdev_install_git_hooks)

```
%%capture
# remove metadata from your notebooks when you commit reducing the chance you have a conflict.
! nbdev_install_git_hooks
# if you do get a conflict, simply run nbdev_fix_merge filename.ipynb
```

#### Settings.ini

Everything is included in the template for the library to be packaged.

Your settings.ini is where all parts of nbdev look for any required configuration information. 

Complete the python form below to update the `settings.ini` file.

Really, only the '**folder_name**' and '**github_username**' fields need to be edited for this to work.

The form values entered here will be inserted into the settings.ini doc. 

```
#@title Example form fields
%nbdev_collapse_input close
#@markdown Forms support many types of fields.

# Name of the project
folder_name = "test123"  #@param {type:"string"}
company_name = "BNIA-JFI" #@param {type:"string"}
# Github Username
github_username = 'karpatic'  #@param {type:"string"}
description = "Data notebooks"  #@param {type:"string"}
keywords = "Python Data Notebooks"  #@param {type:"string"}
# Who are you
author = "Charles Karpati"  #@param {type:"string"}
author_email = 'charles.karpati@gmail.com' #@param {type:"string"}
# Where are your notebooks? Currently at the basepath
path_to_locate_notebooks = "notebooks"  #@param {type:"string"}
# Where should documentation be put? {type:"string"}
path_to_place_documentation = "docs" #@param {type:"string"}
#@markdown ---

user=github_username
nbs_path=path_to_locate_notebooks
doc_path=path_to_place_documentation
lib_name=folder_name

# Now lets rewrite the settings.ini file

innertext = """
[DEFAULT]
# All sections below are required unless otherwise specified
host = github
lib_name = """+lib_name+"""
company_name = """+company_name+"""

user = """+user+"""
description = """+description+"""
keywords = """+keywords+"""
author = """+author+"""
author_email = """+author_email+"""
copyright = MIT
branch = master
version = 0.0.1
min_python = 3.6
audience = Developers
language = English
# Set to True if you want to create a more fancy sidebar.json than the default
custom_sidebar = False
# Add licenses and see current list in `setup.py`
license = apache2
# From 1-7: Planning Pre-Alpha Alpha Beta Production Mature Inactive
status = 2

# Optional. Same format as setuptools requirements
# requirements = 
# Optional. Same format as setuptools console_scripts
# console_scripts = 
# Optional. Same format as setuptools dependency-links
# dep_links = 

###
# You probably won't need to change anything under here,
#   unless you have some special requirements
###

# Change to, e.g. "nbs", to put your notebooks in nbs dir instead of repo root
nbs_path = """+nbs_path+"""
doc_path = """+doc_path+"""

# Anything shown as '%(...)s' is substituted with that setting automatically
doc_host =  https://%(user)s.github.io
#For Enterprise Git pages use:  
#doc_host = https://pages.github.%(company_name)s.com.  


doc_baseurl = /%(lib_name)s/
# For Enterprise Github pages docs use:
# doc_baseurl = /%(repo_name)s/%(lib_name)s/

git_url = https://github.com/%(user)s/%(lib_name)s/tree/%(branch)s/
# For Enterprise Github use:
#git_url = https://github.%(company_name)s.com/%(repo_name)s/%(lib_name)s/tree/%(branch)s/



lib_path = %(lib_name)s
title = %(lib_name)s

#Optional advanced parameters
#Monospace docstings: adds <pre> tags around the doc strings, preserving newlines/indentation.
#monospace_docstrings = False
#Test flags: introduce here the test flags you want to use separated by |
#tst_flags = 
#Custom sidebar: customize sidebar.json yourself for advanced sidebars (False/True)
#custom_sidebar = 
#Cell spacing: if you want cell blocks in code separated by more than one new line
#cell_spacing = 
#Custom jekyll styles: if you want more jekyll styles than tip/important/warning, set them here
#jekyll_styles = note,warning,tip,important
"""

# Write-Overwrites 
file1 = open("settings.ini", "w")  # write mode 
file1.write(innertext) 
file1.close() 
```

    UsageError: Invalid option "close". Usage `%nbdev_collapse_input [open]`


#### Edit The Notebooks

To start, notice how there are two `.ipynb`'s. 

These are two notebooks used for the template.

1. `index.ipynb` - When index.ipynb gets converted to 'index.html' it becomes the documentations homepage since browsers understand 'index.html' to be a websites homepage. When published, this notebook will also be made into the README.md document that can be shown for github repositories pages and on Pypi. Once published to Pypi, the index notebook (the homepage) can be used to show others how to install and use the library!

2. `00_core.ipynb` - This is the 'core' component of the python library. You don't have to keep the 'core' part. The left two digits in the filename help the website navigation so you can increment your notebooks by the order you want them displayed. The index.ipynb is the only notebook that does not have this logic apply to it. Inside the notebook you will see a template near ready for deployment. If the lib_name was to be replaced and a function was declared with an `# export flag` at the top of its cell; this would be ready for deployment and publishing to Pypi!

```
%nbdev_hide_output
! mkdir ./notebooks
! mv ./00_core.ipynb ./notebooks/
! mv index.ipynb ./notebooks/
```

```
%nbdev_hide_output
! mkdir ./notebooks
! rm ./00_core.ipynb
! mv index.ipynb ./notebooks/
```

#### Create the library and documentation

Install libraries used in your exported module here, now, or else the next part wont work.

For now, since we are working with start template, this should not be a problem.

Once ready, run `! nbdev_build_lib`

- You'll now find that you have a new directory, with the name of whatever you set lib_name to.

```
%nbdev_hide_output
! nbdev_build_lib
```

```
# ! nbdev_nb2m index.ipynb
```

**Congratulations**! You have now successfully created a python library. 

This library is empty though. In order to export code be sure to use the `#export` Flag on cells.

Be sure to explore the Flags and Commands!

#### Configuring Git-Github

```
%nbdev_hide_output
! git init
```

In order to [add an existing project](https://docs.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line) to github: 
- [Create a new repository](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository) with the repositories name the same as the new library.
- Ensure the repository is absolutely empty so we can make a clean push!

One you do create the github repo through  website, you can connect the your git repo to the github repo using this command

Mentioning an exported class with backticks `functionName` will create a hyperlink to its documentation. 

```
# Make the replacements where needed and run this! be sure to remove our password once ran.

# ! git remote add ORIGIN https://<USER NAME>:<passwrd>@github.com/<USER NAME>/<REPO NAME>.git
```

You will now be able to commit this local repository to the to github.

#### Create a PyPi account

In order for you to be able to publish to [Pypi](https://pypi.org/), you must have an account with them.

Click register on the top right corner of their website to do that.

Your username should be the `user` value from your settings.ini file.

#### Publishing!

Refer to the Build Proccess, Pypi & Git sections below.

## NBDEV Operations

( Run Once Modules, Docs and the README are created using NBDEV and are ready to publish to the web )

you need to install the libraries in this nb that are used in your other nb.

```
%%capture
# 1_ACS EXPLORE AND DOWNLOAD
!pip install -U -q ipywidgets
!pip install geopandas
!jupyter nbextension enable --py widgetsnbextension
```

```
%%capture
# 02_Merge_Data.ipynb
!pip install geopandas
!pip install dataplay
!pip install dexplot
```

Enter the project if it exists. Otherwise go to the folder you want it to exist at.

```
cd datalabs
```

As long as you are somewhere in the folder where you are developing your library. Both of these commands will work:

```
# nbdev_build_lib, builds the library from the notebooks
!nbdev_build_lib
```

    Converted 00_github.ipynb.
    Converted 01_colabs.ipynb.
    Converted 02_scooterExploration.ipynb.
    Converted 03_nbdev.ipynb.
    Converted index.ipynb.


```
# nbdev_build_docs builds the documentation from the notebooks
!nbdev_build_docs
```

    <IPython.core.display.HTML object>
    <IPython.core.display.HTML object>
    converting: /content/drive/My Drive/datalabs/notebooks/03_nbdev.ipynb
    converting: /content/drive/My Drive/datalabs/notebooks/index.ipynb
    <IPython.core.display.HTML object>
    <IPython.core.display.HTML object>
    converting: /content/drive/My Drive/datalabs/notebooks/02_scooterExploration.ipynb
    converting: /content/drive/My Drive/datalabs/notebooks/01_colabs.ipynb
    converting: /content/drive/My Drive/datalabs/notebooks/00_github.ipynb
    <IPython.core.display.HTML object>
    <IPython.core.display.HTML object>
    <IPython.core.display.HTML object>
    <IPython.core.display.HTML object>
    converting /content/drive/My Drive/datalabs/notebooks/index.ipynb to README.md


## Git

**Before you push**: Running `nbdev_clean_nbs` will ensure the push will work. `nbdev_fix_merge` ensures it.

```
! nbdev_clean_nbs
! nbdev_fix_merge notebooks/00_github.ipynb
! nbdev_fix_merge notebooks/01_colabs.ipynb
! nbdev_fix_merge notebooks/02_scooterExploration.ipynb
! nbdev_fix_merge notebooks/03_nbdev.ipynb
! nbdev_fix_merge notebooks/index.ipynb
```

    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_clean_nbs", line 8, in <module>
        sys.exit(nbdev_clean_nbs())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/clean.py", line 87, in nbdev_clean_nbs
        clean_nb(nb, clear_all=clear_all)
      File "/usr/local/lib/python3.6/dist-packages/nbdev/clean.py", line 51, in clean_nb
        for c in nb['cells']: clean_cell(c, clear_all=clear_all)
    KeyError: 'cells'
    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_fix_merge", line 8, in <module>
        sys.exit(nbdev_fix_merge())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/merge.py", line 98, in nbdev_fix_merge
        shutil.copy(fname, fname.with_suffix('.ipynb.bak'))
      File "/usr/lib/python3.6/shutil.py", line 245, in copy
        copyfile(src, dst, follow_symlinks=follow_symlinks)
      File "/usr/lib/python3.6/shutil.py", line 120, in copyfile
        with open(src, 'rb') as fsrc:
    FileNotFoundError: [Errno 2] No such file or directory: 'notebooks/00_github.ipynb'
    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_fix_merge", line 8, in <module>
        sys.exit(nbdev_fix_merge())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/merge.py", line 98, in nbdev_fix_merge
        shutil.copy(fname, fname.with_suffix('.ipynb.bak'))
      File "/usr/lib/python3.6/shutil.py", line 245, in copy
        copyfile(src, dst, follow_symlinks=follow_symlinks)
      File "/usr/lib/python3.6/shutil.py", line 120, in copyfile
        with open(src, 'rb') as fsrc:
    FileNotFoundError: [Errno 2] No such file or directory: 'notebooks/01_colabs.ipynb'
    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_fix_merge", line 8, in <module>
        sys.exit(nbdev_fix_merge())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/merge.py", line 98, in nbdev_fix_merge
        shutil.copy(fname, fname.with_suffix('.ipynb.bak'))
      File "/usr/lib/python3.6/shutil.py", line 245, in copy
        copyfile(src, dst, follow_symlinks=follow_symlinks)
      File "/usr/lib/python3.6/shutil.py", line 120, in copyfile
        with open(src, 'rb') as fsrc:
    FileNotFoundError: [Errno 2] No such file or directory: 'notebooks/02_scooterExploration.ipynb'
    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_fix_merge", line 8, in <module>
        sys.exit(nbdev_fix_merge())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/merge.py", line 98, in nbdev_fix_merge
        shutil.copy(fname, fname.with_suffix('.ipynb.bak'))
      File "/usr/lib/python3.6/shutil.py", line 245, in copy
        copyfile(src, dst, follow_symlinks=follow_symlinks)
      File "/usr/lib/python3.6/shutil.py", line 120, in copyfile
        with open(src, 'rb') as fsrc:
    FileNotFoundError: [Errno 2] No such file or directory: 'notebooks/03_nbdev.ipynb'
    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_fix_merge", line 8, in <module>
        sys.exit(nbdev_fix_merge())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 103, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/merge.py", line 98, in nbdev_fix_merge
        shutil.copy(fname, fname.with_suffix('.ipynb.bak'))
      File "/usr/lib/python3.6/shutil.py", line 245, in copy
        copyfile(src, dst, follow_symlinks=follow_symlinks)
      File "/usr/lib/python3.6/shutil.py", line 120, in copyfile
        with open(src, 'rb') as fsrc:
    FileNotFoundError: [Errno 2] No such file or directory: 'notebooks/index.ipynb'


```
! nbdev_clean_nbs
```

    /bin/bash: nbdev_clean_nbs: command not found


```
!nbdev_nb2md -h
```

    /bin/bash: nbdev_nb2md: command not found


```
! nbdev_nb2md notebooks/00_github.ipynb --dest "markdown" --img_path "."
! nbdev_nb2md notebooks/01_colabs.ipynb --dest "markdown" --img_path "."
! nbdev_nb2md notebooks/02_scooterExploration.ipynb --dest "markdown" --img_path "."
! nbdev_nb2md notebooks/03_nbdev.ipynb --dest "markdown" --img_path "."
! nbdev_nb2md notebooks/index.ipynb --dest "markdown" --img_path "."
```

( Run Once Modules, Docs and the README are created using NBDEV and have ben created but not published )

```
# cd datalab
```

```
! git add *
```

    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    The following paths are ignored by one of your .gitignore files:
    build
    dist
    Use -f if you really want to add them.


```
ls
```

    [0m[01;34mbuild[0m/           [01;34mdist[0m/    Makefile     [01;34mnotebooks[0m/    setup.py
    CONTRIBUTING.md  [01;34mdocs[0m/    MANIFEST.in  README.md
    [01;34mdatalabs[0m/        LICENSE  [01;34mmarkdown[0m/    settings.ini


```
!git config --global user.name "karpatic"
```

```
!git config --global user.email "charles.karpati@gmail.com"
```

```
! git commit -m "Updated Formating, Added Markdown Section"
```

    [master d0a5ecb] Updated Formating, Added Markdown Section
     23 files changed, 7975 insertions(+), 4009 deletions(-)
     rewrite docs/scooterExploration.html (61%)
     create mode 100644 markdown/00_github.md
     create mode 100644 markdown/01_colabs.md
     create mode 100644 markdown/02_scooterExploration.md
     create mode 100644 markdown/03_nbdev.md
     create mode 100644 markdown/index.md
     create mode 100644 markdown/output_102_1.png
     create mode 100644 markdown/output_103_1.png
     create mode 100644 markdown/output_109_1.png
     create mode 100644 markdown/output_30_1.png
     create mode 100644 markdown/output_37_2.png
     rewrite notebooks/03_nbdev.ipynb (68%)


```
# git push -f origin master
```

```
! git push -u ORIGIN master
```

    Counting objects: 27, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (26/26), done.
    Writing objects: 100% (27/27), 2.38 MiB | 2.68 MiB/s, done.
    Total 27 (delta 17), reused 0 (delta 0)
    remote: Resolving deltas: 100% (17/17), completed with 13 local objects.[K
    remote: 
    remote: GitHub found 1 vulnerability on karpatic/datalabs's default branch (1 high). To find out more, visit:[K
    remote:      https://github.com/karpatic/datalabs/network/alert/docs/Gemfile.lock/kramdown/open[K
    remote: 
    To https://github.com/karpatic/datalabs.git
       56b1bad..d0a5ecb  master -> master
    Branch 'master' set up to track remote branch 'master' from 'ORIGIN'.


If you get the error "fatal: could not read Username for 'https://github.com': No such device or address"...

You will need to re-establish your git-github connection. Run: `! git remote rm ORIGIN`

and then re-add like so `! git remote add ORIGIN https://<USER NAME>:<passwrd>@github.com/<USER NAME>/<REPO NAME>.git`.

Be sure to make the replacements where needed and run this! be sure to remove our password once ran.

If Github pages does not show consult this [guide](https://docs.github.com/en/github/working-with-github-pages/troubleshooting-jekyll-build-errors-for-github-pages-sites#troubleshooting-build-errors). Typically this is a problem with the markdown.

## PyPI

( Run Once Modules, Docs and the README are created using NBDEV and have ben created )

Be sure you have a Pypi account that has the same username as your github account before continuing.

You could save your credentials into a .pypirc file, but I don't recommend it.

```
# ! echo "[pypi]" > .pypirc
# ! echo "username = 'username'" >> .pypirc
# ! echo "password = 'password'" >> .pypirc
```

To publish to Pypi, install twine.

```
%%capture
! pip install twine
```

Be sure to run this final nbdev command `! nbdev_bump_version` prior to publishing. Otherwise you might have issues.

```
!nbdev_bump_version
```

Other than that...

Nbdev has everything else all set up! Simply run make pypi and enter your credentials when prompted (at the bottom of the terminal output). Your password will be sensored so it is safe to post this code online without clearing it.

```
%nbdev_hide_output
! make pypi
```

    rm -rf dist
    python setup.py sdist bdist_wheel
    running sdist
    running egg_info
    creating datalabs.egg-info
    writing datalabs.egg-info/PKG-INFO
    writing dependency_links to datalabs.egg-info/dependency_links.txt
    writing entry points to datalabs.egg-info/entry_points.txt
    writing top-level names to datalabs.egg-info/top_level.txt
    writing manifest file 'datalabs.egg-info/SOURCES.txt'
    reading manifest template 'MANIFEST.in'
    warning: no previously-included files matching '__pycache__' found under directory '*'
    writing manifest file 'datalabs.egg-info/SOURCES.txt'
    running check
    creating datalabs-0.0.2
    creating datalabs-0.0.2/.github
    creating datalabs-0.0.2/.github/workflows
    creating datalabs-0.0.2/datalabs
    creating datalabs-0.0.2/datalabs.egg-info
    creating datalabs-0.0.2/docs
    creating datalabs-0.0.2/docs/_data
    creating datalabs-0.0.2/docs/_data/sidebars
    creating datalabs-0.0.2/docs/_includes
    creating datalabs-0.0.2/docs/_layouts
    creating datalabs-0.0.2/docs/css
    creating datalabs-0.0.2/docs/css/fonts
    creating datalabs-0.0.2/docs/fonts
    creating datalabs-0.0.2/docs/images
    creating datalabs-0.0.2/docs/js
    creating datalabs-0.0.2/docs/licenses
    creating datalabs-0.0.2/notebooks
    copying files to datalabs-0.0.2...
    copying .gitignore -> datalabs-0.0.2
    copying CONTRIBUTING.md -> datalabs-0.0.2
    copying LICENSE -> datalabs-0.0.2
    copying MANIFEST.in -> datalabs-0.0.2
    copying Makefile -> datalabs-0.0.2
    copying README.md -> datalabs-0.0.2
    copying settings.ini -> datalabs-0.0.2
    copying setup.py -> datalabs-0.0.2
    copying .github/workflows/main.yml -> datalabs-0.0.2/.github/workflows
    copying datalabs/__init__.py -> datalabs-0.0.2/datalabs
    copying datalabs/_nbdev.py -> datalabs-0.0.2/datalabs
    copying datalabs/core.py -> datalabs-0.0.2/datalabs
    copying datalabs.egg-info/PKG-INFO -> datalabs-0.0.2/datalabs.egg-info
    copying datalabs.egg-info/SOURCES.txt -> datalabs-0.0.2/datalabs.egg-info
    copying datalabs.egg-info/dependency_links.txt -> datalabs-0.0.2/datalabs.egg-info
    copying datalabs.egg-info/entry_points.txt -> datalabs-0.0.2/datalabs.egg-info
    copying datalabs.egg-info/not-zip-safe -> datalabs-0.0.2/datalabs.egg-info
    copying datalabs.egg-info/top_level.txt -> datalabs-0.0.2/datalabs.egg-info
    copying docs/.gitignore -> datalabs-0.0.2/docs
    copying docs/Gemfile -> datalabs-0.0.2/docs
    copying docs/Gemfile.lock -> datalabs-0.0.2/docs
    copying docs/_config.yml -> datalabs-0.0.2/docs
    copying docs/colabs.html -> datalabs-0.0.2/docs
    copying docs/feed.xml -> datalabs-0.0.2/docs
    copying docs/github.html -> datalabs-0.0.2/docs
    copying docs/index.html -> datalabs-0.0.2/docs
    copying docs/nbdev.html -> datalabs-0.0.2/docs
    copying docs/scooterExploration.html -> datalabs-0.0.2/docs
    copying docs/sidebar.json -> datalabs-0.0.2/docs
    copying docs/sitemap.xml -> datalabs-0.0.2/docs
    copying docs/tooltips.json -> datalabs-0.0.2/docs
    copying docs/_data/alerts.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/definitions.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/glossary.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/tags.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/terms.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/topnav.yml -> datalabs-0.0.2/docs/_data
    copying docs/_data/sidebars/home_sidebar.yml -> datalabs-0.0.2/docs/_data/sidebars
    copying docs/_includes/archive.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/callout.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/footer.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/google_analytics.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/head.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/head_print.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/image.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/important.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/initialize_shuffle.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/inline_image.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/links.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/note.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/search_google_custom.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/search_simple_jekyll.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/sidebar.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/tip.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/toc.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/topnav.html -> datalabs-0.0.2/docs/_includes
    copying docs/_includes/warning.html -> datalabs-0.0.2/docs/_includes
    copying docs/_layouts/default.html -> datalabs-0.0.2/docs/_layouts
    copying docs/_layouts/default_print.html -> datalabs-0.0.2/docs/_layouts
    copying docs/_layouts/none.html -> datalabs-0.0.2/docs/_layouts
    copying docs/_layouts/page.html -> datalabs-0.0.2/docs/_layouts
    copying docs/_layouts/page_print.html -> datalabs-0.0.2/docs/_layouts
    copying docs/css/bootstrap.min.css -> datalabs-0.0.2/docs/css
    copying docs/css/boxshadowproperties.css -> datalabs-0.0.2/docs/css
    copying docs/css/customstyles.css -> datalabs-0.0.2/docs/css
    copying docs/css/font-awesome.min.css -> datalabs-0.0.2/docs/css
    copying docs/css/modern-business.css -> datalabs-0.0.2/docs/css
    copying docs/css/printstyles.css -> datalabs-0.0.2/docs/css
    copying docs/css/syntax.css -> datalabs-0.0.2/docs/css
    copying docs/css/theme-blue.css -> datalabs-0.0.2/docs/css
    copying docs/css/theme-green.css -> datalabs-0.0.2/docs/css
    copying docs/css/fonts/FontAwesome.otf -> datalabs-0.0.2/docs/css/fonts
    copying docs/css/fonts/fontawesome-webfont.eot -> datalabs-0.0.2/docs/css/fonts
    copying docs/css/fonts/fontawesome-webfont.svg -> datalabs-0.0.2/docs/css/fonts
    copying docs/css/fonts/fontawesome-webfont.ttf -> datalabs-0.0.2/docs/css/fonts
    copying docs/css/fonts/fontawesome-webfont.woff -> datalabs-0.0.2/docs/css/fonts
    copying docs/css/fonts/fontawesome-webfont.woff2 -> datalabs-0.0.2/docs/css/fonts
    copying docs/fonts/FontAwesome.otf -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/fontawesome-webfont.eot -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/fontawesome-webfont.svg -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/fontawesome-webfont.ttf -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/fontawesome-webfont.woff -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/glyphicons-halflings-regular.eot -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/glyphicons-halflings-regular.svg -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/glyphicons-halflings-regular.ttf -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/glyphicons-halflings-regular.woff -> datalabs-0.0.2/docs/fonts
    copying docs/fonts/glyphicons-halflings-regular.woff2 -> datalabs-0.0.2/docs/fonts
    copying docs/images/company_logo.png -> datalabs-0.0.2/docs/images
    copying docs/images/company_logo_big.png -> datalabs-0.0.2/docs/images
    copying docs/images/doc_example.png -> datalabs-0.0.2/docs/images
    copying docs/images/export_example.png -> datalabs-0.0.2/docs/images
    copying docs/images/favicon.ico -> datalabs-0.0.2/docs/images
    copying docs/images/workflowarrow.png -> datalabs-0.0.2/docs/images
    copying docs/js/customscripts.js -> datalabs-0.0.2/docs/js
    copying docs/js/jekyll-search.js -> datalabs-0.0.2/docs/js
    copying docs/js/jquery.ba-throttle-debounce.min.js -> datalabs-0.0.2/docs/js
    copying docs/js/jquery.navgoco.min.js -> datalabs-0.0.2/docs/js
    copying docs/js/jquery.shuffle.min.js -> datalabs-0.0.2/docs/js
    copying docs/js/toc.js -> datalabs-0.0.2/docs/js
    copying docs/licenses/LICENSE -> datalabs-0.0.2/docs/licenses
    copying docs/licenses/LICENSE-BSD-NAVGOCO.txt -> datalabs-0.0.2/docs/licenses
    copying notebooks/00_github.ipynb -> datalabs-0.0.2/notebooks
    copying notebooks/01_colabs.ipynb -> datalabs-0.0.2/notebooks
    copying notebooks/02_scooterExploration.ipynb -> datalabs-0.0.2/notebooks
    copying notebooks/03_nbdev.ipynb -> datalabs-0.0.2/notebooks
    copying notebooks/index.ipynb -> datalabs-0.0.2/notebooks
    Writing datalabs-0.0.2/setup.cfg
    creating dist
    Creating tar archive
    removing 'datalabs-0.0.2' (and everything under it)
    running bdist_wheel
    running build
    running build_py
    creating build
    creating build/lib
    creating build/lib/datalabs
    copying datalabs/core.py -> build/lib/datalabs
    copying datalabs/__init__.py -> build/lib/datalabs
    copying datalabs/_nbdev.py -> build/lib/datalabs
    installing to build/bdist.linux-x86_64/wheel
    running install
    running install_lib
    creating build/bdist.linux-x86_64
    creating build/bdist.linux-x86_64/wheel
    creating build/bdist.linux-x86_64/wheel/datalabs
    copying build/lib/datalabs/core.py -> build/bdist.linux-x86_64/wheel/datalabs
    copying build/lib/datalabs/__init__.py -> build/bdist.linux-x86_64/wheel/datalabs
    copying build/lib/datalabs/_nbdev.py -> build/bdist.linux-x86_64/wheel/datalabs
    running install_egg_info
    Copying datalabs.egg-info to build/bdist.linux-x86_64/wheel/datalabs-0.0.2-py3.6.egg-info
    running install_scripts
    adding license file "LICENSE" (matched pattern "LICEN[CS]E*")
    creating build/bdist.linux-x86_64/wheel/datalabs-0.0.2.dist-info/WHEEL
    creating 'dist/datalabs-0.0.2-py3-none-any.whl' and adding 'build/bdist.linux-x86_64/wheel' to it
    adding 'datalabs/__init__.py'
    adding 'datalabs/_nbdev.py'
    adding 'datalabs/core.py'
    adding 'datalabs-0.0.2.dist-info/LICENSE'
    adding 'datalabs-0.0.2.dist-info/METADATA'
    adding 'datalabs-0.0.2.dist-info/WHEEL'
    adding 'datalabs-0.0.2.dist-info/entry_points.txt'
    adding 'datalabs-0.0.2.dist-info/top_level.txt'
    adding 'datalabs-0.0.2.dist-info/RECORD'
    removing build/bdist.linux-x86_64/wheel
    twine upload --repository pypi dist/*
    /bin/sh: 1: twine: not found
    Makefile:23: recipe for target 'pypi' failed
    make: *** [pypi] Error 127


```
ls
```
