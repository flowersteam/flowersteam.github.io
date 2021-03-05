# Few tips to add a post on the page

If you want to run the server locally clone the repo and install jekyll:

https://jekyllrb.com/

Then add the following lines to the Gemfile:

```
gem 'jekyll-sitemap'
gem 'jekyll-paginate'
gem 'jekyll-admin', group: :jekyll_plugins
```

Before running the command 
```
bundle exec jekyll serve
```

you might have to delete the Gemfile.lock.

Be carefull you should not push the modifications to the Gemfile on the repo when you add your post.

When pushing, only add the files you modified '.md', '.css', images etc..




