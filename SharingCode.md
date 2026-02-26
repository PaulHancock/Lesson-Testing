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
