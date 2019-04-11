## _assets

> One common solution is to create a folder in the root of the project directory called something like assets, into which any images, files or other resources are placed. 
> 
> ### Example:
> 
> ```
> ... which is shown in the screen shot below:
> ![My help screenshot](/assets/screenshot.jpg)
> ```

## Displaying an index of posts

```
<ul>
{ % for post in site.posts % }
 <li>
  <a href="{{ post.url }}"> {{ post.title }</a>
 </li>
 { % endfor % }
</ul>
```
# Metadata

The front matter of a page/post often accomodates metadata, including the built-in ones as below:  
- categories  
- tags  

## Categories & Tags

### What's the difference?

A category can be part of a url for a post while a tag cannot.

An example:  
> ```
> ---
> layout: post
> title: A Trip
> categories: [blog, travel]
> tags: [hot, summer]
> ---
> ```

`[blog, travel]` is actually a list, which can be converted to the below expression in yaml:  
```
categories:
 - blog
 - travel
```

- Categories availale at *site.categories*  
- 

Access a post's content by using `exceprt` variable on a post. By default, this is the first paragraph of content in the post, however it can be customized by setting a `excerpt_separator` variable in fronot matter or `_config.yml`
[Click here for more](https://www.jekyll.com.cn/docs/posts/)

