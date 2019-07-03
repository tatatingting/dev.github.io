# tatatingting.github.io
tingting's blog https://tatatingting.github.io/





## intro

it's source: https://github.com/tatatingting/tatatingting.github.io

there're three branches:

- master (published, honored one)
- dev (tools, bugs and cool-jokes)
- gh-pages (not in use anymore, just for fun and remember)



## work with Jekyll

there're topics about Jekyll:

- very beginning of **local Jekyll**
- key points about Jekyll **theme**





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

4. (recommended) change the filepath for clear info:

    ```
    cd dev
    ```
    
    
    
5. Install Jekyll and other [dependencies](https://pages.github.com/versions/) from the GitHub Pages gem:

    ```
    bundle install
    ```
    
    if there's no local gemfile, just create one.

    - create a file named 'Gemfile' and content as follows:

        ```
        source 'https://rubygems.org'
        gem 'github-pages', group: :jekyll_plugins
        ```

    then run `bundle install` again.

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






