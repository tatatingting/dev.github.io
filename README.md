# tatatingting.github.io

tingting's blog https://tatatingting.github.io/

its source: https://github.com/tatatingting/tatatingting.github.io



> ./dev.github.io

this source is used to output the _site for the blog



## intro

this source https://github.com/tatatingting/dev.github.io

now the source is 

there're three branches:

- master (published, honored one)
- dev (tools, bugs and cool-jokes)
- gh-pages (not in use anymore, just for fun and remember)



## play with Jekyll

###sketch the game

there're topics about Jekyll:

- step-by-step local build (v2.0)

- quick-start (v1.1)
- very beginning of local Jekyll (v1.0)
- key points about Jekyll theme



###details

####quick-start

1. install Git

2. install Ruby + devkit ==>  `ruby --version`

3. install Bundler ==> `gem install bundler`

4. Install Jekyll and other dependencies from the GitHub Pages gem ==> `bundle install`

   tip: create file just named "Gemfile" 没有扩展名 and the content:

    ```
    source 'https://rubygems.org'
    gem 'github-pages', group: :jekyll_plugins
    ```

5. run Jekyll locally ==> `bundle exec jekyll serve`

6. browse to  http://localhost:4000/

7. try ==> `bundle exec jekyll new myblog`



####step-by-step local build

have a look at the structure:

```
.sass-cache
├── _authors
├── _data
├── _includes
├── _layouts
├── _posts
├── _sass
├── _site
├── assets
|   ├── css
|   ├── images
|   └── js
_config.yml
about.md
blog.html
Gemfile
Gemfile.lock
index.html
staff.html
...
```

Note that any time you update `_config.yml` you’ll need to restart Jekyll for the changes to take affect.

more see https://jekyllrb.com/docs/step-by-step/01-setup/

- ready for production https://jekyllrb.com/docs/step-by-step/10-deployment/

- This restricts your Ruby environment to only use gems set in your `Gemfile`.

  ```
  bundle exec jekyll serve
  ```

- deployment by 3rd party like GitHub Pages, Note that GitHub Pages runs in `safe` mode and only allows [a set of whitelisted plugins](https://help.github.com/articles/configuring-jekyll-plugins/#default-plugins).

  To use the currently-deployed version of the gem in your project, add the following to your `Gemfile`:

  ```
  source "https://rubygems.org"
  
  gem "github-pages", group: :jekyll_plugins
  ```

  Be sure to run `bundle update` often.



**very beginning of local Jekyll**

- https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll

1. install Git. open `Git Bash`.

2. install Ruby + devkit. if not please go to download [Ruby 2.1.0 or higher](https://www.ruby-lang.org/en/downloads/).

    ```
    ruby --version
    ```

3. install Bundler:

    ```
    gem install bundler
    ```

4. (optional) change the filepath for clear info:

    ```
    cd dev
    ```
    
    
    
5. Install Jekyll and other [dependencies](https://pages.github.com/versions/) from the GitHub Pages gem, run the line:

    ```
    bundle install
    ```
    
    if "Could not locate Gemfile", just create one.

    - create a file named 'Gemfile' and content as follows:

        ```
        source 'https://rubygems.org'
        gem 'github-pages', group: :jekyll_plugins
        ```

    then run the line again.

    then wait ...:alarm_clock: ...

    - if too long, consider about the source problem, you can change the source by edit the file or run the line for mirror + no-need-change-source:

        ```
    bundle config mirror.https://rubygems.org https://gems.ruby-china.com
        bundle install
        ```
    
    - if successfully, you'll see or maybe not see, it doesn't matter:

        ```
    Post-install message from html-pipeline:
        -------------------------------------------------
        Thank you for installing html-pipeline!
        You must bundle Filter gem dependencies.
        See html-pipeline README.md for more details.
        https://github.com/jch/html-pipeline#dependencies
        -------------------------------------------------
        
        Bundle complete!
        ```
    
    

6. build your local Jekyll site, and aumatully create a new file named 'myblog':

    ```
    bundle exec jekyll new myblog
    ```

    

7. change the filepath to run the local Jekyll:

    ```
    cd myblog
    ```

    

8. (finally) run the local Jekyll locally:

    ```
    bundle exec jekyll serve
    ```

    now, 👏  browse to  http://localhost:4000/ and enjoy:)

    

9. (optional) how to update with the GitHub Pages gem? pls try:

    ```
    bundle update github-pages
    ```

    or

    ```
    gem update github-pages
    ```





**key points about Jekyll theme**

- https://help.github.com/en/articles/customizing-css-and-html-in-your-jekyll-theme
- 






