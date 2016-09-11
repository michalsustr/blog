---
layout: single
title: Sphinx - python tips
created: 2016-07-20
categories:
- python
---
I recently started to educate myself more in Python. I decided that from time to time I'm going to put here some tips and tricks, things that I've come across that I think are interesting. These are comments from a person who has quite a lot of experience with other languages, such as Java, PHP and Matlab. I'll put up links to these articles on twitter under hashtag #pythontips, so if you like these you can just follow the hashtag.

Sphinx
------

I started to work on a new project and since I have quite a free hand at what I'm doing, I decided to do things right. One of the most important things in any project is its documentation. 

I searched for what would be nice in Python, actually there's a huge list of different [documentation generator systems on wikipedia](https://en.wikipedia.org/wiki/Comparison_of_documentation_generators) Searching on the web I found Sphinx, seemed quite nice so I gave it a try.

In my conda installation all I had to do is:

```
$ conda install sphinx
# and then follow this set-up tutorial
$ sphinx-quickstart
```

It is going to ask you bunch of questions - if you want to generate docs from code, don't forget to allow **autodoc**

Useful links:

- Here is a link to tutorial: <https://codeandchaos.wordpress.com/2012/07/30/sphinx-autodoc-tutorial-for-dummies/>
- How to write code for .rst files: <https://pythonhosted.org/an_example_pypi_project/sphinx.html>
- Use markdown instead of rst: <http://searchvoidstar.tumblr.com/post/125486358368/making-pdfs-from-markdown-on-readthedocsorg-using>
(I didn't get that to work properly yet, but others seem to have)
- All kinds of options: <http://www.sphinx-doc.org/en/stable/domains.html>

I set up my project with following structure

```
├── data
├── docs        # here is Sphinx documentation
│   ├── _build
│   ├── conf.py
│   ├── index.rst
│   ├── make.bat
│   ├── Makefile
│   ├── _static
│   └── _templates
├── Makefile
├── NOTES.md
├── README.md
├── requirements.txt
├── src              # my main code
├── temp
└── tests
```

`conf.py` has all of the Sphinx config, the one that you setup in the `spinhx-quickstart`. Find `sys.path.insert` and add `sys.path.insert(0, os.path.abspath('../src'))`

My main project Makefile has these scripts:

```
# I wanted to have it called docs, but that confuses make command
# since there is a directory there already called docs - these two have to be distinct.
doc: 
	# remove all old rst files except index.rst
	find ./docs -name '*.rst' ! -name 'index.rst' -type f -exec rm -f {} \;
	# generate new .rst files for docs
	sphinx-apidoc -l -F --module-first -o docs src
	# vrrrrruuummm!!! generate docs
	cd docs; make html;

showdoc:
	chromium-browser docs/_build/html/index.html
```

That's it, I just type `make doc` and then `make showdoc` and the documentation is born. Voila!



