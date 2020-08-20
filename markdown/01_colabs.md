# Python and Colabs



> In this chapter we will quickly learn about Github and explore some of its many features. 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/karpatic/datalab/master?filepath=%2Fnotebooks%2F01_colabs.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/colab.svg)](https://colab.research.google.com/github/karpatic/datalab/blob/master/notebooks/01_colabs.ipynb)
[![Binder](https://pete88b.github.io/fastpages/assets/badges/github.svg)](https://github.com/karpatic/datalab/tree/master/notebooks/01_colabs.ipynb)
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

A free, book covering python data science with notebooks may be found [here](https://jakevdp.github.io/PythonDataScienceHandbook/). It uses jupyter notebooks of which colabs is built off of.

Information for this section was pulled from a variety of resources. Click the links to learn more!

## The Colab environment

  Before getting into gritty details, take a moment to explore the Colab environment.

Setup & Configuration:

1. Begin by visiting https://colab.research.google.com
2. Click 'NEW PYTHON 3 NOTEBOOK'
3. For the most part, thats all it takes! 

4. Many modules are already pre-installed on the virtual enviornment.





The following articles can help get you started. Excerpts have been selected and shown in block quotes.


### [Welcome](https://colab.research.google.com/notebooks/intro.ipynb#scrollTo=-Rh3-Vt9Nev9) to Colaboratory

> Colaboratory, or "Colab" for short, allows you to write and execute Python in your browser, with
 - Zero configuration required
 - Free access to GPUs
 - Easy sharing

> The document you are reading is not a static web page, but an interactive environment called a Colab notebook that lets you write and execute code.

> To execute the code... use the keyboard shortcut "Command/Ctrl+Enter". 

```
# the hash symbol at the front of this line means its a comment.
# comments show up in green and will not be interpreted upon code execution. 
# In this example we will perform a simple computation to see its output below

1  + 1
```

```
# Notice how the output is now stored in the 
# 'madeUpVariable' and 'evenMoreMadeUpVariable' variables
# and will not show give an output below.
madeUpVariable = 1  + 1
evenMoreMadeUpVariable = 13.5
```

```
# Variable values persist across blocks (both above and below).
# So always make sure your variables use the correct values!

# Also, Take note! 
# Output is hidden unless placed on the last line or 
# wrapped in a 'Print' function like so
print(evenMoreMadeUpVariable)

# So none of this will show but still run.
evenMoreMadeUpVariable * evenMoreMadeUpVariable

# But this will show too since its on the last line.
madeUpVariable
```

> Colab notebooks allow you to combine [markup](#markup), executable code, and text into a single document, along with images, HTML, LaTeX and more. When you create your own Colab notebooks, they are stored in your Google Drive account. You can easily share your Colab notebooks with co-workers or friends, allowing them to comment on your notebooks or even edit them. To learn more, see Overview of Colab. To create a new Colab notebook you can use the File menu above, or use the following link:create a new Colab notebook.
 > Colab notebooks are Jupyter notebooks that are hosted by Colab. To learn more about the Jupyter project, see jupyter.org.

*All blockquotes in the section above was pulled from the header's link*

### Colab Menu Bar

Everything you need can be found in your menu bar. 

A brief outline below:

<image src="https://charleskarpati.com/images/ColabMenu.png" alt="Colabs Menu" title="Colab Menu" height="300"/>

File (accessible on the left hand drawer)
- Locate in drive
- New, Open, Upload
- Save, Download, **Save to Github** or Drive

Edit
- Undo
- Select all, cut, copy, paste, delete
- **Find, Replace** 
- **Show/ Hide** all code
- **Clear all** code outputs

View
- Table of Contents (accessible on the left hand drawer)
- Executed Code history
- Diff Notebooks
- Collapse sections

Insert
- Code/ Text cell
- Section header
- **Code Snippet** (accessible on the left hand drawer)

Runtime
- Run - Execute all cells, or just before or after or at a selected cell.
- **Interrupt execution** - Just in case the code is caught in an eternal loop or is hanging.
- Restart (and optionally re-run all) - Installed modules are kept but must be re-imported.
- **Factory reset** runtime - Must re-install all modules

Tools
- Command Palette - Clickable menu of shortcuts
- Settings
- - **Site** - Set theming
- - **Editor** - Set indentation, fontsize, line width
- - **Misc** - Enable 'Corgie' and or 'Kittie' Mode.
- Keyboard Shortcuts

Help
- [FAQ](https://research.google.com/colaboratory/faq.html) 
- Ask a question on [Stack](https://stackoverflow.com/users/login?ssrc=anon_ask&returnurl=https%3a%2f%2fstackoverflow.com%2fquestions%2fask%3ftags%3dgoogle-colaboratory) Overflow

### [Overview](https://colab.research.google.com/notebooks/basic_features_overview.ipynb) of Colaboratory Features

*Features in the header link's article are accessible from the Menu Bar.*

> Colaboratory... magics... are shorthand annotations that change how a cell's text is executed.

Much more on this is covered [below](#magics). But...

Observe what you can do with it:

```
%%html
<marquee style='width: 30%; color: blue;'>
    Here, we use python magics in the first line of this code-block to have the remaining lines display HTML
</marquee>
```

As well, With magics, you can execute terminal [commands](https://colab.research.google.com/github/jakevdp/PythonDataScienceHandbook/blob/master/notebooks/01.05-IPython-And-Shell-Commands.ipynb) straight from a code block!

preface your terminal command with a "!" so the interpreter knows the text is not python.

```
!ls
```

Stand alone, single line terminal commands to not actually need to be prefaced with an `!`

```
ls
```

The output responce from the execution of a of terminal command can even be stored as python variables!

```
cow = !ls
cow
```

**More Tricks**

- Other advanced code [tricks](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)
- Hosting notebooks online using github and [mybinder](https://mybinder.org/)
- Notebooks can also be **colab**oratively edited by sharing a link on Google Drive
- Colabs can connect to and run on your [local machine](https://research.google.com/colaboratory/local-runtimes.html)

### <a name="markup"></a> Markup

> In computer text processing, a markup language is a system for annotating a document in a way that is syntactically distinguishable from the text,[1] meaning when the document is processed for display, the markup language is not shown, and is only used to format the text. -[wikipedia](https://en.wikipedia.org/wiki/Markup_language)

#### <a name="markdown"></a>Markdown [Guide](https://colab.research.google.com/notebooks/markdown_guide.ipynb)

A) **Markdown is the name given to markup used for making text rich-text**. 

B) Text cells (not code-cells) in **colab will automatically understand markdown** and display it appropriately. 

C) Within Colabs, <b><u><i>many HTML elements can readily be rendered</i></u></b>  within markdown cells like the enriched text in this sentence.
- This is not a given on other markdown viewers and can be prevented by encapsulating the html **`<u>with backticks</u>`** . 

**Badges**

Badges are (typically) action-enabled icons used to call attention to the reader. 

These are often displayed using HTML or Markdown.

Pick a template and create your own badge from [shields.io](https://shields.io/category/social) to get started!



**More on Markdown**:
- Markdown Vs. [Markup](https://stackoverflow.com/questions/24041/markdown-vs-markup-are-they-related#:~:text=Markdown%20is%20a%20play%20on,Markdown%22%20is%20a%20proper%20noun.&text=Markup%20is%20a%20general%20term,library%20that%20generates%20HTML%20markup.)
- Generic Github [Guide](https://guides.github.com/features/mastering-markdown/)
- [Basic](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax) writing and formatting syntax
- Writing on [GitHub](https://help.github.com/en/github/writing-on-github)

#### Flags: <a name="magics"></a> Magics and Comments

A. **'Flags' are a special form of shorthand annotation that change how code-block's are executed**.

B. These annotations augment the [interpreter]( https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FInterpreter_%28computing%29)s handling of a cell or line.

C. Flags are placed [on the first line]( https://ipython.readthedocs.io/en/stable/interactive/magics.html#cell-magics ) or on a [per line basis](https://ipython.readthedocs.io/en/stable/interactive/magics.html#line-magics) depending on intent

D. There exists two types of Flags: Comment and [Magics](https://www.tutorialspoint.com/google_colab/google_colab_magics.htm)

1) **Magics** is often identified by two `%`'s at the top of the document followed by the intendid magical affect. 

2) **Comments** use a single `#` and are less favored since the `#` symbol is already [overloaded](https://en.wikipedia.org/wiki/Function_overloading). 

- Under normal circumstances, a `#` will preface a numeral, whats more,
- Markdown uses `#`'s to denote a header element.

**Common Uses**: 

A) Create section titles from within a codeblock using `#@title <TITLENAME>` 

B) Suppress cell output using `%%capture`.

C) Execute terminal commands in a cell by prefacing it with the `!` line-magics.

D) Comment-ify a line in your code using the `#`' prefix.

E) Render the cell as `%%html` or `%%javascript` or a single line with `#@markdown`.

F) Creating input forms by placing the line-magics `#@param {type:"DATA-TYPE"}` at the end of a variable declaration.

## The Python Enviornment

### Preface:

- Here is as quick overview of notable [features](https://wiki.python.org/moin/BeginnersGuide/Overview) 

- This is the official [documentation](https://docs.python.org/3/) and [tutorial](https://docs.python.org/3/tutorial/index.html)

- And this website w3schools provide great introductory [tutorials](https://www.w3schools.com/python/) with examples

- This Python Wiki [Beginners Guide](https://wiki.python.org/moin/BeginnersGuide) provides a ton of helpful links. It has guides for [programmers](https://wiki.python.org/moin/BeginnersGuide/Programmers) and [nonprogrammers](https://wiki.python.org/moin/BeginnersGuide/NonProgrammers).


Now that we understand a bit more about Colab lets address the following questions.

### What is [Python](https://www.python.org/doc/essays/blurb/)? 

(emphasis my own)
> Python is an **interpreted**, **object-oriented**, **high-level** programming language with dynamic semantics. Its high-level built in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development, as well as for use as a scripting or glue language to connect existing components together. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance. Python **supports modules** and packages, which encourages program modularity and code reuse. The Python interpreter and the extensive standard library are available in source or binary form without charge for all major platforms, and can be freely distributed.

> Often, programmers fall in love with Python because of the increased productivity it provides. Since there is **no compilation** step, the edit-test-debug cycle is **incredibly fast**. Debugging Python programs is easy:a bug or bad input will never cause a segmentation fault. Instead, **when the interpreter discovers an error, it raises an exception. When the program doesn't catch the exception, the interpreter prints a stack trace. A source level debugger allows inspection of local and global variables, evaluation of arbitrary expressions, setting breakpoints, stepping through the code a line at a time, and so on**. The debugger is written in Python itself, testifying to Python's introspective power. On the other hand, often the quickest way to debug a program is to add a few print statements to the source: the fast edit-test-debug cycle makes this simple approach very effective.

### What makes Python high-level?

- Because it's not assembly or as a series of ones and zeroes.
- Memory management is made automatic. 

### What makes Python [Object-Oriented](https://www.tutorialspoint.com/python/python_classes_objects.htm)?

- Basically, everything in python is an object!
- Well get back to this but heres a peek

```
# import a module
import json

# create some data as text or a 'String':
x =  '{ "name":"John", "age":30, "city":"New York"}'

# use the JavaScript Object Notation (JSON) module to parse x:
y = json.loads(x)

# the result yields a Python dictionary. 
# It was converted from a string of text (data) that was encoded using JSON notation:
print(y["age"])
```

More information on JSON:
- [Official](https://www.json.org/json-en.html)
- [Guide](https://www.w3schools.com/js/js_json_intro.asp)

### What makes Python interpreted?

1. Machines run on machine code and Python needs some way to be translated to machine code.
2. When you execute a line of python code, the process of interpreting the python code and translating ([compiling](https://en.wikipedia.org/wiki/Compiler)) it to machine code happens in real time.
3. While all languages need to be interpreted, the real-time compilation during code execution is why python is called an interpreted as apposed to compiled language.

'Installing python' is really just the process of installing an interpreter 
- Colab comes with a built in interpreter that runs every time a cell runs.
- Use this guide to learn more about local [installation](https://wiki.python.org/moin/BeginnersGuide/Download).

Python files can be imported for use in other scripts or interpretated directly using a python terminal command. 
- ```python ./path/to/file/nameOfFile.py```

### Whats the difference between Python 2 and Python 3? 

Shouldnt matter! 

It used to. But Python 2 is depricated now. Everyone should be using Python 3. 

If your computer comes with python built in, chances are it came with Python 2. Finagling with two versions of python can be a pain since they use different notations. 

*With colabs this is simply not a problem because of they are brand new virtualized enviornments every time*

### What are modules?

> A module is a Python object with arbitrarily named attributes that you can bind and reference. Simply, a module is a file consisting of Python code. A module can define functions, classes and variables. A module can also include runnable code.... You can use any Python source file as a module by executing an import statement in some other Python source file. - [TutorialsPoint](https://www.tutorialspoint.com/python/python_modules.htm#:~:text=A%20module%20is%20a%20Python,can%20also%20include%20runnable%20code.)
'Package' is a term often used to describe a suite of modules.

### What is PIP and PyPi?

> pip is a de facto standard package-management system used to install and manage software packages written in Python. Many packages can be found in the default source for packages and their dependencies — Python Package Index ([PyPI](https://pypi.org/)). Most distributions of Python come with pip preinstalled. Python 2.7.9 and later (on the python2 series), and Python 3.4 and later include pip (pip3 for Python 3) by default. - [Wikipedia](https://en.wikipedia.org/wiki/Pip_(package_manager)#cite_note-rhos-pip-4)
If you find Python code you like on Github, see if it can be found on PyPi.

If so type ```pip install package``` into the terminal to install the module.  

Once installed, you can now 'import' the package in your python code.

For more information on PIP, check out this cool [guide](https://www.w3schools.com/python/python_pip.asp)

> To import a library that's not in Colaboratory by default, you can use `!pip install` or `!apt-get install`. - [Snippets:Importing Libraries](https://colab.research.google.com/notebooks/snippets/importing_libraries.ipynb)

### Pandas

Colab comes with pip pre installed. Check it out its use in the cell below

```
!pip install pandas
```

Congratulations! You've installed [Pandas](https://pandas.pydata.org/).

```
# Now that pandas has been installed on the virtual enviornment. 
# Import it as a module into your codes memory! A bit redundent I know.
# In this instance we are assigning the pandas module to the variable 'pd'
import pandas as pd
```

Pandas provides tools for data analysis. 

as an example, lets import some JSON data!

```
# to use the pandas module, we refer to it by its namespace
# In this example, we use the pandas 'read_json' function to prepare our json for data play.  
pd.read_json('{"row 1":{"col 1":"a","col 2":"b"},"row 2":{"col 1":"c","col 2":"d"}}', orient='index')
```

You can do awesome things with data when it is being interpreted as a 'dataframe'. Take a look

```
newlyCreatedDataframeVariable = pd.read_json('{"row 1":{"col 1":"a","col 2":"b"},"row 2":{"col 1":"c","col 2":"d"}}', orient='index')
```

```
# Show the first row
newlyCreatedDataframeVariable.head()
```

```
# make a copy of the dataset
variable2 = newlyCreatedDataframeVariable.copy()
```

```
# Show the first row
variable2.tail(2)
```

```
variable2['col 1']
```

```
# This would save the file as a CSV onto wherever the virtual enviornment is mounted.
# This may be the temporary mount-point, or google drive/ local hard drive.
#variable2.to_csv(index=False)
```

Pandas works with bunch of great utilities like [Dexplot](https://github.com/dexplo/dexplot) and [Geopandas](https://geopandas.org/) for enhanced visualizations.

A more thorough introduction to pandas on colabs can be found [here](https://colab.research.google.com/notebooks/mlcc/intro_to_pandas.ipynb)
> Learning Objectives:- Gain an introduction to the DataFrame and Series data structures of the pandas library  - Access and manipulate data within a DataFrame and Series
  - Import CSV data into a pandas DataFrame
  - Reindex a DataFrame to shuffle data

Be sure to take a look at its online [library](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html), provided to help you along the way!

### [External Data](https://colab.research.google.com/notebooks/io.ipynb)

The most simple way to access your data is by mounting Google Drive to your Virtual Enviornment

```
# Run this. 
# Click the link that shows itself. 
# Give permission. 
# Copy the link and paste it back here.
from google.colab import drive
drive.mount('/content/drive')
```

```
cd ./drive/'My Drive'/colabs/DATA
```

```
ls
```

You can store a users input as a value like so:

```
left_on = input("Left on: " )
```

A neat trick to get form values can be done like so:

```
#@title Example form fields
#@markdown Forms support many types of fields.

filename = 'concrete.csv'  #@param
displayColumn = 'Cement'  #@param {type: "string"}
multiplyer2 = 100  #@param {type: "slider", min: 100, max: 200}
multiplyer1 = 102  #@param {type: "number"}
variable5 = '2010-11-05'  #@param {type: "date"}
variable6 = "monday"  #@param ['monday', 'tuesday', 'wednesday', 'thursday']
displayColumn2 = "Strength" #@param ["Strength", "bananas", "oranges"] {allow-input: true}
#@markdown ---
```

Just be sure to re-run the cell block to update the variable values

```
concreteDataframe = pd.read_csv(filename)
concreteDataframe.head()
```

```
concreteDataframe['NewAttribute'] = (concreteDataframe[displayColumn].head() * multiplyer2) - (concreteDataframe[displayColumn].head() * multiplyer1)
concreteDataframe.head()
```

### Putting it together

[dataplay](https://karpatic.github.io/dataplay/) is a package I'm working on to help work with data. It provides tools and tutorials for data manipulation.

With this package, you can install ACS data with relative ease.

```
! pip install dataplay geopandas
```

```
from dataplay.acsDownload import retrieve_acs_data 

# Define our download parameters.
# more information on these parameters can be found in the tutorials!
tract = '*'
county = '510'
state = '24'
tableId = 'B19001'
year = '17'
saveAcs = False

retrieve_acs_data(state, county, tract, tableId, year, saveAcs).head(2)
```

```
# Get the Second dataset. 
# Our Example dataset contains Polygon Geometry information. 
# We want to merge this over to our principle dataset. we will grab it by matching on either CSA or Tract

# The url listed below is public.

print('Crosswalk Example: https://docs.google.com/spreadsheets/d/e/2PACX-1vREwwa_s8Ix39OYGnnS_wA8flOoEkU7reIV4o3ZhlwYhLXhpNEvnOia_uHUDBvnFptkLLHHlaQNvsQE/pub?output=csv')
print('Boundaries Example: https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8xXdUaT17jkdK0MWTJpg3GOy6jMWeaXTlguXNjCSb8Vr_FanSZQRaTU-m811fQz4kyMFK5wcahMNY/pub?gid=886223646&single=true&output=csv')

inFile = input("\n Please enter the location of your file : \n" )

crosswalk = pd.read_csv( inFile )
crosswalk.head()
```

```
import dataplay.mergeData
```

```
# Table: FDIC Baltimore Banks
# Columns: Bank Name, Address(es), Census Tract
left_ds = 'https://docs.google.com/spreadsheets/d/e/2PACX-1vSHFrRSHva1f82ZQ7Uxwf3A1phqljj1oa2duGlZDM1vLtrm1GI5yHmpVX2ilTfMHQ/pub?gid=601362340&single=true&output=csv'
left_col = 'Census Tract'

# Table: Crosswalk Census Communities
# 'TRACT2010', 'GEOID2010', 'CSA2010'
right_ds = 'https://docs.google.com/spreadsheets/d/e/2PACX-1vREwwa_s8Ix39OYGnnS_wA8flOoEkU7reIV4o3ZhlwYhLXhpNEvnOia_uHUDBvnFptkLLHHlaQNvsQE/pub?output=csv'
right_col='TRACT2010'

merge_how = 'outer'
interactive = True
use_crosswalk = True

merged_df = mergeDatasets( left_ds=left_ds, left_col=left_col, 
              right_ds=right_ds, right_col=right_col, 
              merge_how='left', interactive =True, use_crosswalk=use_crosswalk )
```

```
dir(mergeDatasets)
```

```
mergeDatasets
```

```
dir(retrieve_acs_data)
```
