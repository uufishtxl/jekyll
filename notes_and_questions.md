# Pages

The tutorial may be retrieved from [this site](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_pages.html#where-to-save-pages).

## Where to save pages

> The listing of all pages in the root directory (***which happens when you add a permalink property to the pages***) is what allows the relative 
linking and offline viewing of the site to work.

My comment: Actually, not that it matter.

## Front Matter

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
    
### Allowed Components:
| Component | Description |
| ------- | --------- | 
| layout    | Specifies the layout to use. Omit the file extention. |
| permalink | Set the permalink to format the URL address. |
| public | Set to false if you'd like to keep a post to yourself. |

Must-have components in front matter
- title
- permalink
