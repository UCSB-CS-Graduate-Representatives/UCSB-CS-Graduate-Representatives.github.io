[UCSB CS Gradreps website](http://cs.ucsb.edu/~greps/)
==========================================

The new open-source Gradreps website 
------------------------------------

Interested in contributing to [the website](http://cs.ucsb.edu/~greps/)? Curious how it is put together? Want to use it as a building block to create your own? Here's how!

This website is run on [GitHub pages](https://pages.github.com/), a free hosting service for static pages. Content is written in a simple human-readable markdown format, organized in a straightforward directory structure. GitHub (or rather: [Jekyll](https://help.github.com/articles/using-jekyll-with-pages/), the engine powering this) does the heavy lifting of translating the entire package into a static website.

This sytem makes editing websites extremely easy, and the raw markdown (.md) files you'll spend most of your time editing are human-friendly with no code, just content. Content files are writting in markdown and completely separate from the html and css code. Afterwards, all of the content and presentation code gets merged together by script and out pops a static website.

[Full story here](http://daringfireball.net/projects/markdown/) on the markdown syntax

The layout of the project in the repository is something like the following, seen from the root of the project:

* who-we-are, what-we-are, bylaws, contact, positions, etc:
These folders are the main pages of the website, and each contain an index.md file. The markdown file references what html layout it should use (see _layouts below), and the rest of it is pure content written with a markdown syntax that get's translated into html.

* _layouts:
This folder contains the barebones html files which dictate the template for how the content is presented. 

* _includes:
The layouts mentioned above have some shared elements, such as a common header and footer. To minimize copy-pasting, these elements are defined here and *included* in the other files.

* _config.yml in root:
This file contains 'site-wide information', with various variables that are referenced in other places.

* _site (not present in github):
When the static website is created by merging all of the above information, it is placed here.

* _posts:
This folder contains all of the news posts which we want to add to the website. Files must be named according to date: "2014-12-31-Title.md", for example. These get automatically added to the front page.

* _GradReps:
A *collection* defined in _config.yml as a variable of the same name. Files in this directory are added to the collection. They can be iterated over to create a list of all of the GradReps, and each one gets an associated webpage. 

If you want to play around with this then I heavily recommend [downloading Jekyll](https://help.github.com/articles/using-jekyll-with-pages/). With that, you can run a local server on your machine and view changes you make in these files as soon as you save them. When you have a configuration you like, you can push the changes to GitHub, and the github.io webpage will update. To run a local server using Jekyll, see the [information provided here](http://jekyllrb.com/docs/usage/).
