# Markdown Site Configs

<!-- > 2018-08-06T20:58:02+0800 -->

An example of configurations for the [Markdown Site Generator](https://github.com/zhanbei/Markdown-Site-Generator) with the [github flavored markdown](https://github.github.com/gfm/) supported.

## Requirements

Make sure you have

- the [`MarkdownSiteGenerator`](https://github.com/zhanbei/Markdown-Site-Generator) installed and have the command `generate-md-site`.
	- This command is used to generate site based on markdown files.
- the [`static-server`](https://github.com/zhanbei/static-server) installed and have the command `static-server`.
	- This command is used to host the generated site in the no-trailing-slash mode.

## Start a Brand New Blog

Here is instructions to start a brand new blog using configures from this repo:

```bash
# Create a folder for your blogs.
mkdir My-Awesome-Blog
cd My-Awesome-Blog

# Git clone this repository of configures.
git clone https://github.com/zhanbei/.markdown-site-configs.git .site_configs

# Write something in markdown.
echo -e "# A Post for Test\n\n0. This is a test blog.\n0. Built by Markdown-Site-Generator." >> A-Test-Blog.md
echo -e "# A Post about Myself\n\nA blog about myself, but here is nothing really useful currently." >> About.md


# Build your blog site.
# generate-md-site .
generate-md-site .site_configs

# Check out what has been generated in the .site folder.
tree .site

# MANUALLY Copy static assets to your .site; this will be fixed later.
cp -r .site_configs/github/assets/ .site/

# Start the static server and your site will be hosted at http://localhost:1234/
static-server --no-trailing-slash 1234 .site
```

With the site successfully hosted, you may open your browser and check out your site.
