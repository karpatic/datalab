# Nbdev
> In this chapter we learn about publishing python notebooks with <a href='http://nbdev.fast.ai/tutorial/'>nbdev</a>.


[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/karpatic/datalab/master?filepath=%2Fnotebooks%2Findex.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/colab.svg)](https://colab.research.google.com/github/karpatic/datalab/blob/master/notebooks/index.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/github.svg)](https://github.com/karpatic/datalab/tree/master/notebooks/index.ipynb)
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

## (Non-Technical) Introduction

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![ForTheBadge built-with-love](http://ForTheBadge.com/images/badges/built-with-love.svg)](https://GitHub.com/Naereen/) [![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)

[![ForTheBadge powered-by-electricity](http://ForTheBadge.com/images/badges/powered-by-electricity.svg)](http://ForTheBadge.com)

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

### <a name="nbflags"></a> Nbdev Flags (Mark Up/ Cell Magic) 

Nbdev scripts rely on special [comments **or** magics](https://nbdev.fast.ai/tutorial/#nbdev-flags) (your choice) for cell-level handling of notebooks.

Whereas Nbdev's terminal commands should be executed at a projects root directory...

Content covered in this section need to be placed in the cells of the notebooks.

Most nbdev flags define design instructions for when we create the website/ module. Some flags (`default_exp`, `autoreload`) 

**1.** **Basic Comment and Magics**

{% include warning.html content='Content in this section is pulled from the Fastpages [blog](https://fastpages.fast.ai/fastpages/jupyter/2020/02/21/introducing-fastpages.html#Other-Feautures) [posts](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/07/24/nbdev-deep-dive.html) and the Nbdev docs. If you have any issues, you will have to scoure these sources to resolve them!' %}

To gain access to [Nbdev's new 'magics'](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/06/02/nbdev-magic.html) you my find it neccesary to:
1. Execute the command `nbdev_upgrade`, only once, and then..
2. Add `from nbdev import *` to the top of a notebook in a code-cell.
This [article](https://pete88b.github.io/fastpages/nbdev/fastai/jupyter/2020/06/02/nbdev-magic.html) covers that. 
3. Put Flags at the top of a cell for it to work!

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
| `collapse_output open` or `collapse-output` | `nbdev_collapse_output`     | Inlcude output in the docs under a collapsable element                         |
| `collapse_input close` or `collapse-input` | `nbdev_collapse_output`     | Inlcude input in the docs under a collapsable element                         |
| `collapse_show` or `collapse-show`     | `nbdev_collapse_input open` | Inlcude input in the docs under a collapsable element that is open by default |
| `collapse_hide` or `collapse-hide`     | `nbdev_collapse_input`      | Inlcude input in the docs under a collapsable element                         |
| `collapse`                             | `nbdev_collapse_input`      | Inlcude input in the docs under a collapsable element                         |

**2**: **Autoreloading** : (I have note tried)
> Since you'll be often updating your modules from one notebook, and using them in another, it's helpful if your notebook automatically reads in the new modules as soon as the python file changes. 


First run this in the notebook you want to update:`notebook2script()`

Then this to the top of your notebook as a code cell:

```
%load_ext autoreload
%autoreload 2
```



**3. Console Scripts** are made by marking up functions using the [fastscript](https://fastscript.fast.ai/) tool and editing the settings.ini file ([example](https://github.com/fastai/nbdev/blob/554e63b1b05390a3ad2bc086d8485f98b1e63ca4/settings.ini) )


**4. Anchor Links**
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



**5**: **Jekyll Automated Document Hyperlinking** : 

Mentioning an exported class with backticks `functionName` will create a hyperlink to its sourcode on github (only if its an exported function).

- Functions and Classes have are automatically documented. 

- Class methods are not shown by default, though, so use [`show_doc(class.method`)](http://nbdev.fast.ai/showdoc/#show_doc) to do this.

**6.** **Jekyll Metadata**

The cell `#default_exp` cell located at the top of a cell can also be used for
[YAML](https://yaml.org/), a data-serialization standard, used as [Front Matter](https://assemble.io/docs/YAML-front-matter.html), that can be [used with Jekyll](https://jekyllrb.com/docs/datafiles/) to render templates.
> In the markdown cell with the title, you can add the summary as a block quote (just put an empty block quote for an empty summary) and a list with any additional metadata you would like to add **[`get_metadata`](https://nbdev.fast.ai/export2html/#get_metadata)**

**7. Jekyll Images**

The 'images' folder can be used to conjure up pictures like so:

`![](notebookfolder/images/company_logo.png)`

These images will be added to added and displayed in the docs

![](../../images/ai_of_me.jpg)

**8. Jekyll [Notes](http://nbdev.fast.ai/export2html/#add_jekyll_notes)**

The following section was written using the following markups 

```> Note:```, ```> Warning:```, ```> Tip:``` and ```> Important: text goes here```
{% include note.html content='This is a note.' %}{% include warning.html content='This is a warning' %}{% include tip.html content='This is a tip' %}{% include important.html content='This is an Important doc link to [`add_jekyll_notes`](/export2html#add_jekyll_notes) which should also work fine' %}

**9. Jekyll [Search](http://nbdev.fast.ai/search/)** functionality is not covered here, but may be added.

**10. Jekyll Custom Sidebar**'s for your HTML documentation can be configured using meta-markup, [JSON](https://www.json.org/json-en.html).

> The default sidebar lists all html pages with their respective title, except the index that is named "Overview". To build a custom sidebar, set the flag custom_sidebar in your settings.ini to True then change the sidebar.json file in the doc_folder to your liking. Otherwise, the sidebar is updated at each doc build.

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
! cd Sites/datalabs/notebooks
```

## Creating a New Project

The nbdev library will only work in projects that have the proper file structure and files. 

Once configured, you may simple write in a notebook (placing Nbdev 'FLAGS' where needed) and publish using an Nbdev terminal commands. The Nbdev command will process the notebook and each of its cells according to rules denoted by the 'FLAGS'.

### Getting a template

You can grab a free project template (containing all the needed files and proper structure) to get you started in one of two methods shown below.

#### Method 1) Grabbing a template using github and the browser

Now create a new [repository](https://github.com/fastai/nbdev_template/generate)

```
#hide_output
! git clone https://github.com/karpatic/thisisatemplate.git
```

#### Method 2) Grabbing a template using the Nbdev library and the terminal

An Nbdev terminal command can be used to **create a template** project directory.

Use -h to view positional args.

```
#collapse_output
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
#collapse_input open
! git config --global user.email "charles.karpati@gmail.com"
! git config --global user.name "karpatic"
```

And now you can just **run the command to create a new project**/ (and directory) by a name of your choosing.

```
#hide_output
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
#collapse_input
#@title Example form fields
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

#### Edit The Notebooks

To start, notice how there are two `.ipynb`'s. 

These are two notebooks used for the template.

1. `index.ipynb` - When index.ipynb gets converted to 'index.html' it becomes the documentations homepage since browsers understand 'index.html' to be a websites homepage. When published, this notebook will also be made into the README.md document that can be shown for github repositories pages and on Pypi. Once published to Pypi, the index notebook (the homepage) can be used to show others how to install and use the library!

2. `00_core.ipynb` - This is the 'core' component of the python library. You don't have to keep the 'core' part. The left two digits in the filename help the website navigation so you can increment your notebooks by the order you want them displayed. The index.ipynb is the only notebook that does not have this logic apply to it. Inside the notebook you will see a template near ready for deployment. If the lib_name was to be replaced and a function was declared with an `# export flag` at the top of its cell; this would be ready for deployment and publishing to Pypi!

```
! mkdir ./notebooks
! mv ./00_core.ipynb ./notebooks/
! mv index.ipynb ./notebooks/
```

```
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
#hide_output
! nbdev_build_lib
```

**Congratulations**! You have now successfully created a python library. 

This library is empty though. In order to export code be sure to use the `#export` Flag on cells.

Be sure to explore the Flags and Commands!

#### Configuring Git-Github

```
#hide_output
! git init
```

In order to [add an existing project](https://docs.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line) to github: 
- [Create a new repository](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository) with the repositories name the same as the new library.
- Ensure the repository is absolutely empty so we can make a clean push!

One you do create the github repo through  website, you can connect the your git repo to the github repo using this command

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

    /content/drive/My Drive/Sites/datalabs/datalabs


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
#hide_output
# nbdev_build_docs builds the documentation from the notebooks
!nbdev_build_docs --force_all True --mk_readme True 
```

```
cd notebooks
```

    /content/drive/My Drive/Sites/datalabs/notebooks


```
#hide_output
! nbdev_clean_nbs
! nbdev_fix_merge 00_github.ipynb
! nbdev_fix_merge 01_colabs.ipynb
! nbdev_fix_merge 02_scooterExploration.ipynb
! nbdev_fix_merge 03_nbdev.ipynb
! nbdev_fix_merge index.ipynb
! nbdev_clean_nbs
! find . -name "*.bak" -type f -delete
```

```
#hide_output
# nbdev_nb2md(fname:"A notebook file name to convert", dest:"The destination folder"='.', img_path:"Folder to export images to"='', jekyll:"To use jekyll metadata for your markdown file or not"=False)
! nbdev_nb2md 00_github.ipynb --dest "../markdown" 
! nbdev_nb2md 01_colabs.ipynb --dest "../markdown" 
! nbdev_nb2md 02_scooterExploration.ipynb --dest "../markdown" 
! nbdev_nb2md 03_nbdev.ipynb --dest "../markdown" 
! nbdev_nb2md index.ipynb --dest "../markdown" 
! find . -type d -name "*files" -exec rm -rf {} \;
```

    Traceback (most recent call last):
      File "/usr/local/bin/nbdev_nb2md", line 8, in <module>
        sys.exit(nbdev_nb2md())
      File "/usr/local/lib/python3.6/dist-packages/fastcore/script.py", line 104, in _f
        tfunc(**merge(args, args_from_prog(func, xtra)))
      File "/usr/local/lib/python3.6/dist-packages/nbdev/export2html.py", line 671, in nbdev_nb2md
        convert_md(fname, dest, jekyll=jekyll, img_path=img_path)
      File "/usr/local/lib/python3.6/dist-packages/nbdev/export2html.py", line 580, in convert_md
        with open(Path(dest_path)/img_path/n, 'wb') as f: f.write(o)
    FileNotFoundError: [Errno 2] No such file or directory: '../markdown/02_scooterExploration_files/output_30_1.png'
    find: ‘./00_github_files’: No such file or directory
    find: ‘./01_colabs_files’: No such file or directory
    find: ‘./02_scooterExploration_files’: No such file or directory
    find: ‘./03_nbdev_files’: No such file or directory
    find: ‘./index_files’: No such file or directory


```
cd ../
```

    /content/drive/My Drive/Sites/datalabs


## Git

**Before you push**: Running `nbdev_clean_nbs` will ensure the push will work. `nbdev_fix_merge` ensures it.

( Run Once Modules, Docs and the README are created using NBDEV and have ben created but not published )

```
# cd datalab
```

```
#hide_output
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
! git commit -m "Cover Photo"
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
    /usr/bin/python3: No module named nbstripout
    error: external filter '"/usr/bin/python3" -m nbstripout' failed 1
    error: external filter '"/usr/bin/python3" -m nbstripout' failed
    [master b06e71c] Trying Notebook Img Folder attempt 2
     4 files changed, 81 insertions(+), 58 deletions(-)
     create mode 100644 docs/images/ai_of_me.jpg


```
# git push -f origin master
```

```
#hide_output
! git push -u ORIGIN master
```

    Counting objects: 9, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (9/9), done.
    Writing objects: 100% (9/9), 1.74 KiB | 446.00 KiB/s, done.
    Total 9 (delta 8), reused 0 (delta 0)
    remote: Resolving deltas: 100% (8/8), completed with 8 local objects.[K
    remote: 
    remote: GitHub found 1 vulnerability on karpatic/datalabs's default branch (1 high). To find out more, visit:[K
    remote:      https://github.com/karpatic/datalabs/security/dependabot/docs/Gemfile.lock/kramdown/open[K
    remote: 
    To https://github.com/karpatic/datalabs.git
       e079cd4..b06e71c  master -> master
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

## Misc Tests

![](../../images/ai_of_me.jpg)

```
#hide_output
! make pypi
```

```
ls
```

```
var = "hide"
var
```




    'hide'



```
#hide
var = "hide"
var
```




    'hide'



```
#hide_input
var = "hide_input"
var
```




    'hide_input'



```
#hide_output
var = "hide_output"
var
```




    'hide_output'



```
#collapse_output
var = "collapse_output"
var
```




    'collapse_output'



```
#collapse_show
var = "collapse_show"
var
```




    'collapse_show'



```
#collapse_hide
var = "collapse_hide"
var
```




    'collapse_hide'



```
#collapse-hide
var = "collapse-hide"
var
```




    'collapse-hide'



```
#collapse_input
var = "collapse_input"
var
```




    'collapse_input'



```
#collapse_input open
var = "collapse_input open"
var
```




    'collapse_input open'



```
#collapse_output
var = "collapse_output"
var
```




    'collapse_output'



```
#collapse_output open
var = "collapse_output open"
var
```




    'collapse_output open'


