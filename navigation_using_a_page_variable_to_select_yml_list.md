> # [Navigation](https://jekyllrb.com/tutorials/navigation/)
> 
> ## [Scenario 5: Using a page variable to select the YAML list](https://jekyllrb.com/tutorials/navigation/#scenario-5-using-a-page-variable-to-select-the-yaml-list) 
> 
> Suppose your sidebar will differ based on various documentation sets. You might have 3 different products on your site, and so you want 3 different sidebars — each unique for that product.
> 
> You can ***store the name of the sidebar list in your page front matter*** and then ***pass that value into the list*** dynamically.
> 
> ### Page Front Matter
> 
> ```
> ---
> title: My page
> sidebar: toc
> ---
> ```
> 
> ### Liquid syntax in the required location:
> 
> ```
> ---
> <ul>
>    {% for item in site.data.samplelist[page.sidebar] %}
>     <li><a href="{{ item.url }}">{{ item.title }}</a></li>
>    {% endfor %}
> </ul>
> ---
> ```
> 
> ### Result
> 
>     - Introduction
>     - Configuration
>     - Deployment
> In this scenario, we want to pass values from the page’s front matter into a for loop that contains a variable. When ***the assigned variable isn’t a string but rather a data reference, you must use brackets (instead of curly braces)*** to refer to the front matter’s value.
> 
> For more information, see Expressions and Variables in Liquid’s documentation. Brackets are used in places where dot notation can’t be used. You can also read more details in this Stack Overflow answer.

Tome's theme is populated with three themes, which fits the scenario above.

Atop the *sidebar.html* reads:  
> ```
> {% assign sidebar = site.data.sidebars[page.sidebar].entries %}
> <ul id="mysidebar" class="nav">
> <li class="sidebarTitle">{{sidebar[0].product}} {{sidebar[0].version}}</li>
> ```

Let's correlate this variable to the value specified in the front matter of a specific page, say, the *about_me.md* file.

We read the front matter from the *about_me.md* file, as follows:  
> ```
> title: About the theme's author
> keywords: documentation theme, jekyll, technical writers, help authoring tools, hat replacements
> last_updated: July 3, 2016
> tags: [getting_started]
> summary: "I have used this theme for projects that I've worked on as a professional technical writer."
> sidebar: mydoc_sidebar
> permalink: mydoc_about.html
> folder: mydoc
> ---
> ```

So [page.sidebar] equals to "mydoc_sidebar".
