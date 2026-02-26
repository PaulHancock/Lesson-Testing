---
title: "Sharing Code To The Wider Community"
teaching: 120 # teaching time in minutes
exercises: 60 # exercise time in minutes
---

::::::::::::::::::::::::::::::::::::::: objectives

- Have confidence to share your code
- Make your code findable and accessible

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- Why should I share my code?
- Where and how can I share my code?
- How can I make my python code easy to obtain/install?

::::::::::::::::::::::::::::::::::::::::::::::::::

## ‘Publishing’ code

Once you have code that you are happy to share among collaborators you should consider publishing this code.

What do we mean by publishing? From least to greatest effort, any of the following could be considered as a definition for publishing code:

1. Copying a version of your code to a public website for others to find and use,
1. Making your version control repository ([github][github], [gitlab][gitlab], [bitbucket][bitbucket]) public so that others can use and reuse your code,
1. Uploading your code to a repository such a [pypi.org][pypi] so that others can easily download/install your software,
1. Archiving a version of your code to a doi minting / storage service such as [zenodo.org][zenodo],
1. Registering your code on a site such as [ascl.net](http://ascl.net/) so that others can find your code,
1. Writing a paper describing an application of your code and submitting for peer review in a science focused journal such as [PASA](https://www.cambridge.org/core/journals/publications-of-the-astronomical-society-of-australia) or [MNRAS](https://academic.oup.com/mnras),
1. Writing a companion paper that describes your code and submitting the paper and code for peer review in a software focused journal such as [A&C](https://www.journals.elsevier.com/astronomy-and-computing) or [JOSS](https://joss.theoj.org/).
From the descriptions above you can see that the different options have slightly different intentions and audiences. We can take an lead from FAIR principles for data, and apply these principles to code.

### Findable

Make code findable by creating a persistent identifier (eg doi) and including metadata. On pypi/zenodo/github you can use tags or topics to identify the software language but also the area of research or methodology that is being used. This makes it easier for people to find code that will suit their needs.

### Accessible

Make code accessible by providing source code, install instructions, and documentation. Testing code on a range of platforms will also increase the accessibility of the code.

### Interoperable

Use standard project templates, coding styles and idioms, and a modular design to allow your code to be used as part of a larger workflow or as a component of another product. This interoperability is useful for others, but will also make it easier for you to build on your own existing solutions.

### Reusable

Make code reusable by providing a license, and indicating

### Reasons not to publish

The following are often given as reasons not to publish code:

| Reason | Counter argument |
| -- | -- |
| I don’t want to have to “support” my code. | Publishing code does not commit you to providing endless support. If you do not intend to reply to  emails, fix bugs, or make updates to the code, simply say so in the README.md file. If this is the case you could invite keen users to fork the repo and provide their own fixes.|
| I don’t want people to steal my good work. | With an appropriate license and attribution request, you can let others use your work while you  benefit from their reuse. If there is a paper that describes or uses the code, you can ask for it to be cited by others, and this will increase the impact of that paper (and your h-index!).|
| My code is a bit hacky and I don’t want others to see it. | Being embarrassed about less-than-perfect code is normal. However, a quick scan of  GitHub will show you that hacked-together code is very common even among professional developers. If your code serves it’s intended purpose then it’s good enough to share. Consider writing a short blurb in the README.md file that clearly state the intended aim of the code, so that you can manage the expectations of your users.|
| I don’t know how to share my code. | It’s not difficult to share code, and it’s easy to learn. This course is one of many (MANY) that take you  through the steps of sharing or publishing code. The small investment to learn how to share code will pay off quickly when you start to discover and use code written by others, get feedback and recognition for your code, or when your computer dies and you need to recover your work.|
| My code contains sensitive IP that I’m not allowed to share. | Good argument! Keep it secure some place. Many of the steps that you would take to  prepare your data for publication are still worth doing to make your code usable within your trusted network.|


## Obtaining a doi from Zenodo.org

You have a piece of code on github, but it is changing over time, and you would like to provide a link to a particular version of the code. This is important for reproducibility of your research work, both for yourself and others.

The Zenodo repository provides a safe, trusted, and citable place to host your code. Zenodo is primarily focused on the storage of data, but this includes: documentation, papers, posters, raw or processed data, source code, and compiled binaries. Zenodo will allow you to version your data but does not provide a version control system such as git. However, Zenodo and Github are friends so you can link them together to get the best of both worlds.

### Sign up to Zenodo

You can create a new Zenodo account using an email address and password, or you can use your [Github][github] or [ORCID](https://orcid.org/) accounts to login. Whatever you choose, you can still link your github/ORCID later and use them to sign in.

### Create a new repository

Once signed in click on the upload button at the top of the page, and then on the next page click “New Upload”

![The zenodo header with and upload link](episodes/fig/sharing/zenodo-banner.png)

The following page will have a lot of details, some of which are mandatory, but most of which are either recommended or optional. Begin by downloading a .zip of your files from Github, and then uploading it to Zenodo. Press the green “start upload” button and then start filling out the rest of the form.

![Uploading your files to zenodo](episodes/fig/sharing/uploading-to-zenodo.png)

As the upload is progressing you can fill in the upload type (Software) and basic information.

Leave the DOI blank, but click the “reserve DOI” button so that you can know what the final DOI will be.

Fill in the remainder of the form and then press “save” at the top of the page, this will make a draft of your repository that you can come back to later and update. When you are finally happy with all the details you can press ‘publish’.

Once your upload has been published you should navigate to the published repository in your uploads list, and select it.

![An example doi for published software on zenodo](episodes/fig/sharing/example-zenodo-doi.png)

The above example is for the Aegean source finding software that I developed. You can see the DOI badge with the full DOI, a link to supplementary material, and the licence. If you click the DOI badge you’ll get a new pane that shows you how to embed this information into a markdown file such as your README.md that you have on your github page!

Below this panel you can also see a box that allows people to cite your code. There is even a box that allows people to get the citation in any format that they need it.

![How to cite from zenodo](episodes/fig/sharing/zenodo-citing.png)

You now have a version of your code which is archived on zenodo and will not change. If you want to update the archive with new versions of the code, Zenodo has the capacity to do this, and will mint a new doi for each version. It is recommended that you don’t make a new doi for every small change you make to your code. A new version for each major or minor version change would be appropriate, or when you have published work that used a particular major/minor/patch version of the code.

Sadly Zenodo is not indexed by [ADS](https://ui.adsabs.harvard.edu/) so you can’t track citations very well from here.

## Registering your code on ascl.net

In the last lesson we saw how to obtain a DOI by uploading a software project to Zenodo. In this lesson we’ll make an entry in the Astrophysics Source Code Library ([ASCL.net](https://ascl.net/)), which is indexed by ADS, and can help you gain an audience, and track citations.

### Submit a code to ASCL

Go to the “submit a code” page [here](https://ascl.net/code/submit).

The page asks for a title, credit (authors/contributors), abstract, and a site list for the code.

The site list should be a list of links to places where people can obtain the code. I highly recommend that you put a link to both your Github and Zenodo repositories. If the code was described in a paper you can put that in the “Preferred Citation Method” section.

![Submitting to ASCL.net](episodes/fig/sharing/ascl-submit.png)

ASCL.net does not store your code. No one will vet the quality of your code. ASCL.net is simply a place to register that some code exists and that you’d like to be acknowledged for creating/contributing. ASCL.net is indexed by ADS so it will get a bibcode in ADS, which can then be used to generate a bibtex entry for people to use when citing your code. Another goal of ASCL.net is to make it easier for people to find your code in the first place. If you haven’t explored the code available here I recommend that you do so now – there are some gems.

You can also get a nice little badge from ASCL to add to your `README.md` file!

## Installing your module via setup.py

In our code directory we specified a `requirements.txt` file that allowed users to easily installed the dependencies for our code. However, if someone wants to run our main script (`sim_catalog`) then they have to be in the code directory. If we want to run the code from some other location on our system then it won’t work. The reason is that we haven’t installed our code as a python module.

Installing a python module will do the following:

- Copy the module directory and files (eg `skysim/*`) to a central location so that python can access them no matter where it’s run from,
    - something like `/home/${USER}/.py3/lib/python3.8/site-packages/`;
- Copy and scripts (eg `sim_sky`) to a similar location so that they can be invoked from anywhere,
    - something like `/home/${USER}/.py3/bin/`;
- Make a note that the module is installed,
    - so that `pip freeze` will report the name/version of the software.

In order to install a python module you need a special file called `setup.py`.

###  Template for `setup.py`

The [python documentation](https://docs.python.org/3/distutils/setupscript.html) covers all the gory details of the how and why of using a `setup.py` file. However, a great place to start is to use a template so we’ll provide one here to get started.


```python
import setuptools
import skysim

with open("README.md", "r", encoding="utf-8") as fh:
    long_description = fh.read()

with open('requirements.txt', 'r') as fh:
    reqs = [line for line in fh.readlines() if not line.startswith('#')]

setuptools.setup(
    name="SkySim",
    version=skysim.__version__,
    author=skysim.__author__,
    author_email="author@example.com",
    description="Simulate sky locations",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="https://github.com/DevOne/sky_sim",
    scripts=['scripts/sim_catalog'],
    python_requires=">=3.6",
)
```

Note the following:

- we import the `skysim` module so that we can read the `__version__` and `__author__` information directly,
- we populate the `long_description` by reading the `README.md` file,
- we read the requirements from the `requirements.txt` file,
- we have set a minimum python version for this program, something that we can’t do with a `requirements.txt` file,
- we have moved the script sim_catalog from the root directory into the `scripts/` directory.

The above notes are in keeping with the good coding practice of not repeating ourselves. All the information is stored in a single location and duplication is minimised.

### Installing the module

For someone to install our software they should do one of the following:

```bash
git clone git@github.com:<gituser>/<projectname>.git
pip install .
```

or just download a `.zip` file from github, unzip it, and then run `pip install .` in the same directory.

The final ‘`.`’ indicates that pip should install the module defined in this directory. Pip will search for a `setup.py` file for the required information.

### Uninstall the module

A user can uninstall the module from anywhere by running:

```bash
pip uninstall SkySim
```

### Developer mode

As a developer it is annoying to have to uninstall/install your module every time you make a change and want to check that things are working. Pip has a nice solution to this which is a developer mode install. Unlike a regular install, the developer mode will not copy files to some python directory, but make symlinks instead. This means that your changes to the files will be immediately used in the installed version of the code. If you move or add files however, you’ll need to uninstall/install the code again.

A developer mode install can be done using the `-e` flag for pip:

```bash
pip install -e .
```

### Upgrading

If users want to upgrade the module they have to download or pull the new version, uninstall the old one, and then install the new one. It can be a little tedious and easy to forget. Luckily there is a python package index pypi.org which pip can look to in order to find different versions of your software. It is thanks to pypi.org that pip knows how to install all the modules that we listed in our `requirements.txt` file. We’ll explore the python package index in the next lesson.