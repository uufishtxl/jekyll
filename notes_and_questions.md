# Getting Hands-on with Jekyll Doc Theme 6.0 (Notes)

The tutorial may be retrieved from [this site](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_pages.html#where-to-save-pages)

1. Download the theme from [here](https://github.com/tomjoht/documentation-theme-jekyll).  
2. Install Jekyll. For Jekyll installation, please click [here](https://ke.qq.com/user/index/index.html#/plan/cid=225259&term_id=100265941) for the Mooc courses and [here](https://docs.google.com/document/d/10vTq4wma4cuC4vzbY-6pshnep8OaoYCDH_UiJthEhYo/edit) for the notes I've made.  
3. Install Bundler.  
4. I prefer to build the theme with gethub-pages gem so that I can publish the site on GitHub Pages later. 
    1. You need Bundler to resolve the dependency conflicts. Use Bundler to install all the needed gems:  
        ```
        bundle update
        ```
    2. Always use this command to build jekyll:
        ```
        bundle exec jekyll serve
        ```
    **Q: Why not simply type `jekyll serve` to run the site service on the local computer?**  
    *A:*   
    > *You cannot use the `jekyll serve` command with this gem due to dependency conflicts between the latest version of Jekyll and GitHub Pages (which are noted [briefly here](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll))*. 
    
## Configuring the sidebar

In this theme, there are several sidebars, which is the essence of what makes this theme unique. While you may tune the sidebar to a specific product, the top navigation bar remains the same, always allowing you to navigate across different products.  
Make change to the sidebar property in each page's front matter.  
```
---
...
sidebar: mydoc_sidebar
...
---
```
The *`sidebar: mydoc_sidebar`* points to the yml configuration file *_data/sidebars/mydoc_sidebar.yml*.  
Note that the sidebar can only have 2 levels. The theme author believes:  
> Deeper nesting goes against usability recommendations  

### Can I turn off the sidebar on specific pages?

Of course you can. To turn off the sidebar for a page, set the page frontmatter tag as `hide_sidebar: true`.  
If you don't declaire a sidebar, the `home_sidebar` file gets used as the default because this is the default specified in the config file *_config.yml*.  
```
    scope:
      path: ""
      type: "pages"
    values:
      layout: "page"
      comments: true
      search: true
      sidebar: home_sidebar
      topnav: topnav
```

### Setting different default sidebars for different folders

Specify your defaults like this:  
```
  scope:
    path: "pages/mydoc"
    type: "pages"
  values:
    layout: "page"
    comments: true
    search: true
    sidebar: mydoc_sidebar
    topnav: topnav
```
This would load `mydoc_sidebar` for each file under *pages/mydoc*. You could set different defaults for different path scopes.

### Sidebar syntax



## Pages

### Where to save pages

> The listing of all pages in the root directory (***which happens when you add a permalink property to the pages***) is what allows the relative 
linking and offline viewing of the site to work.

My comment: Actually, not that it matter.

### Front Matter

**Q: What is Front Matter?**  
*A: A rough equivalent to `<head>` in HTML*

The following is official exaplanation from [Jekyll](https://jekyllrb.com/docs/front-matter/):  
* > Any file that contains a YAML front matter block will be processed by Jekyll as a special file. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines. Here is a basic example:  
    ```
    ---
    layout: post
    title: Blogging Like a Hacker
    ---
    ```
    
#### Allowed Components:
| Component | Description |
| ------- | --------- | 
| layout    | Specifies the layout to use. Omit the file extention. |
| permalink | Set the permalink to format the URL address. |
| public | Set to false if you'd like to keep a post to yourself. |

Must-have components in front matter
- title
- permalink
