# README

Here is a relatively complete set of instructions for setting up a Jekyll site for the first time. For more details, check out the following official resources:
- [Jekyll][https://jekyllrb.com/docs/step-by-step/01-setup/]
- [Ruby][https://gorails.com/setup/osx/10.14-mojave]
- [Jekyll-Scholar][https://github.com/inukshuk/jekyll-scholar]

Jekyll is basically like Latex, but for generating HTML instead of PDF's. Your write your site as a series of HTML files and Markdown documents, where the HTML files are templates with scripts for making headers and footers and assembling the Markdown documents into the final site.

## Installing Homebrew and Ruby
For Jekyll to work, we first have to install Homebrew, which will allow us to set up the full Ruby development environment required by Jekyll. We can do this by just running this command in the Terminal:
`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Now we download and build Ruby:
`brew install rbenv ruby-build`

We should also add rbenv to our bash profile:
`echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile`

`source ~/.bash_profile`

Finally, we install Ruby:
`rbenv install 2.6.3`

`rbenv global 2.6.3`

## Installing Jekyll and bundler
With Ruby set up, this is simple:
`gem install jekyll bundler`

## Create and serve a new site
We will create a new site in a new directory called "myblog," which will have the default "minima" theme:
`jekyll new myblog`

Now we can change into the new directory
`cd myblog`
and build the site and make it available on a local server:
`bundle exec jekyll serve`

Now we can look at the site by browsing to http://localhost:4000.

## Plugins
There are many useful plugins built for Jekyll. One important plugin for an academic site is Jekyll-Scholar, which allows you to automatically generate publications lists, citations and bibliographies from a bibtex file. Jekyll plugins are packaged as Ruby "gems," which are basically like Python packages as far as I can tell. You install them with the command `gem 'plugin'` where plugin is replaced by the actual name of the plugin. For example, `gem 'jekyll-scholar'` downloads and installs Jekyll-Scholar. Every new site comes with a file called `Gemfile`, which can be found in the root directory of the new `myblog` folder you made. This holds all the `gem` commands required to get all the Ruby gems used by your site. To use a new plugin, you have to add the line `gem 'plugin'` to this file. There's already a plugin installed by default when we ran `jekyll new myblog`. It is called `jekyll-feed`. To make sure our new plugin gets installed, we want to add a line that says `gem 'plugin'` right under `gem 'jekyll-feed'`. Then you have to run the command `bundle update` (while still in the `myblog` directory) in order to run this file and get all the new gems. 

The gemfile lets you get all the gems, but doesn't tell Jekyll that you're using them, or make their commands available to you. To do this, you have to find the file `_config.yml`. This is the file that gives Jekyll all the basic information about your site, including the theme and what plugins you are using. If you find the line that says `plugins:`, you will see that `jekyll-feed` is already there. You just want to add another line with the name of your plugin. For Jekyll-Scholar, we want to put `- jekyll/scholar` right below `- jekyll-feed`. For some extremely obscure reason, `- jekyll-scholar` doesn't work, and you have to replace the hyphen with a forward slash in this case.

## Deployment
Now we are ready to deploy the site. We first build the site by executing the command `bundle exec jekyll build` in the terminal (in our `myblog` directory). This builds the HTML files for our site and puts them in a directory called `_site`. Now we just copy the contents of `_site` and put them on any web server.

## Customizing the theme
You can customize any aspect of the HTML template by finding the `_layouts` and `_includes` folders for your theme and copying them to the root directory of your project (e.g., `myblog`). To find these folders, execute `bundle show minima` in the terminal (replacing `minima` with the name of your theme if you are using a different theme). Any files in these folders will be used instead of the original theme files with the same name when the site is built. If you want to leave some of the files alone, don't copy them over. 

You can also customize the stylesheet by first finding the stylesheet for your theme (using `bundle show` as above to find the theme directory). In minima, the stylesheet is `main.css` in the `assets` directory. Now we do the same thing as with the HTML template, copying over the file we want to change, with its directory structure -- in this case, creating a directory called `assets` in our root project directory and putting `main.css` there. But now instead of editing `main.css` directly, we're going to do something a little different, in order to allow updates to the `main.css` file in future versions of the theme. We are going to replace `main.css` in our new folder with a new file called `main.scss`. In this file, we put the required frontmatter for a Jekyll file (two rows of three hyphens), followed by `@import "{{ site.theme }}";`. When we run Jekyll, this will create a new `main.css` file, including all the original theme content. But now we can add additional content to the `main.scss` file, which will be appended to the new style sheet.

There's something weird with how GitHub Pages does its file structure, so if we just do the above in the minima theme it doesn't find our new style commands. We have to also go into `head.html` in the `_includes` directory and replace the stylesheet link with `<link rel="stylesheet" href="{{ root_url }}/assets/main.css">`.