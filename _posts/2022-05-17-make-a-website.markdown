---
layout: post
title:  "Build a Website with HTML, CSS, and Javascript"
date:   2022-05-17 15:50:40
categories: web dev
---
*These are my notes on the Build a Website with HTML, CSS, and Javascript segment of the Programming Basics section of the [Hopper's Roppers](https://www.roppers.org/) Computing Fundamentals course*

Using the demoHtml repo you already forked off of in the first git assignment, convert it to a Github pages site using this guide: <https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site/>

Section one of the linked guide is for "Creating a repository for your site". We already have the repo made from when we forked it, so I think we can safely skip this section this time.

**The next section is "Creating your site":**
Before you can create your site, you must have a repository for your site on GitHub. If you're not creating your site in an existing repository, see "Creating a repository for your site."
	
*Ok, check!*
	
**Step 1: On GitHub, navigate to your site's repository.**
<https://github.com/octophetus/demoHtml>.
	
**Step 2:** Decide which publishing source you want to use. For more information, see "About GitHub Pages."
From the link - The publishing source for your GitHub Pages site is the branch and folder where the source files for your site are stored. If the default publishing source exists in your repository, GitHub Pages will automatically publish a site from that source. The default publishing source for user and organization sites is the root of the default branch for the repository. The default publishing source for project sites is the root of the gh-pages branch.
		
If you want to keep the source files for your site in a different location, you can change the publishing source for your site.
	
**Step 3:** If your chosen publishing source already exists, navigate to the publishing source. If your chosen publishing source doesn't exist, create the publishing source.
All our files are in the root of the repository for demoHtml so let's navigate to that directory (in our case it is currently: /home/octophetus/demoHtml).
		
**Step 4:** In the root of the publishing source, create a new file called index.md that contains the content you want to display on the main page of your site. Tip: If index.html is present, this will be used instead of index.md. If neither index.html nor index.md are present, README.md will be used.
We already have a README.md so why don't we just skip this step for now.
	
**Step 5:** Configure your publishing source. For more information, see "Configuring a publishing source for your GitHub Pages site."
Choosing a publishing source:
Step 5a: On GitHub, navigate to your site's repository.
Step 5b: Under your repo name, click settings
Step 5c: In the "Code and automation" section of the sidebar, click Pages.
Step 5d: Under "GitHub Pages", use the None or Branch drop-down menu and select a publishing source (here we are choosing Branch: main)
Step 5e: Optionally, use the drop-down menu to select a folder for your publishing source (I am choosing directory / root)
	
**Step 6:** Click save
	
**Step 7:** To see your published site, under "GitHub Pages", click your site's URL (<https://octophetus.github.io/demoHtml/>).
			
**Step 8** (added by me, not the guide!): I would go to the main page of your Github repo and in the about section in the upper right, add the URL to the site so you can easily access it.

