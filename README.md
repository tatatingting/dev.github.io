# tatatingting.github.io

tingting's blog https://tatatingting.github.io/



## intro

it's source https://github.com/tatatingting/tatatingting.github.io

there're three branches:

- master (published, honored one)
- dev (tools, bugs and cool-jokes)
- gh-pages (not in use anymore, just for fun and remember)



## .gitignore


```
_site
.sass-cache
.jekyll-metadata
```

## 0 2 1

Part I (v2.1)

- 必须拥有一个 index.html 文件。

- Liquid 可以处理“被朴素传递”的信息：通过上下两排的 `---` 三个短横符号，中间填上：键值对。

  ```
  ---
  # front matter tells Jekyll to process Liquid
  title: Home
  ---
  ```

  

- `_layout` 是模板，其中的 page 指代实例，通过 page.method 调用参数值，通过 content 引用内容。

- `_include` 是 `_layout` 的片段，`_layout` 通过 include 引用。比如：导航部分。

- `_data ` 可以存放 YAML, JSON, CSV 等文件， `_include` 通过 site.data.xxx 引用。比如：遍历导航。

- `assets` 是文件夹，用来放 css, images, js 等文件，`_layout` 通过本地路径引用。比如："link href"。

- sass 是 css 的一个超集，相应的扩展名是  ".scss"。

- `assets/css` 文件夹中有sass文件。 需要组织复杂的css时，可以通过引用 `_sass` 文件夹的内容。

- `_sass` 文件夹也有sass文件。复杂的 css 装饰需要被组织有序，被`assets/css` 引用。

- `_posts` 是放 blogs 的文件夹，里面是 markdown 文件，命名需要参考"2019-07-04-title.md"这个格式。

- blogs 的命名格式，产生了相应的 page.date 和 page.title。

- blogs 可以在文档内再次指定 title，在 page.title 被调用时，文档里的会覆盖文件名提供的。

- blogs 还可以在文档内指定别的东西。 

- blogs 通过语法指定layout，相应的要在 `_layout` 里存在这个模板。比如："post.html"。

- blogs 可以被陈列，比如放在 index.html 里，或者新建一个 blog.html，并手动更新 `_data` 里的导航。

- 





```mermaid
graph TD

_layout

_include -."{% include xx.html %}".-> _layout

_data -."{% for item in site.data.xx %}xx{% endfor %}".-> _include
	YAML --- _data
	JSON --- _data
	CSV --- _data

assets -."link href='assets/xx/xx'".-> _layout
	css --- assets
	image --- assets
	js --- assets

_sass -."@import 'main';".-> css


```

Part II





## (optional) play with Jekyll

### sketch the game

there're topics about Jekyll:

- step-by-step local build (v2.0)

- quick-start (v1.1)
- very beginning of local Jekyll (v1.0)
- key points about Jekyll theme



### details

#### quick-start

1. install Git

2. install Ruby + devkit ==>  `ruby --version`

3. install Bundler ==> `gem install bundler`

4. Install Jekyll and other dependencies from the GitHub Pages gem ==> `bundle install`

   tip: create file just named "Gemfile" 没有扩展名 and the content

   ```shell
   source 'https://rubygems.org'
   gem 'github-pages', group: jekyll_plugins
   ```

   

5. run Jekyll locally ==> `bundle exec jekyll serve`

6. browse to  http://localhost:4000/

7. try ==> `bundle exec jekyll new myblog`



#### step-by-step local build

more see https://jekyllrb.com/docs/step-by-step/01-setup/

have a look at the structure:

    ```shell
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

- ready for production https://jekyllrb.com/docs/step-by-step/10-deployment/

- This restricts your Ruby environment to only use gems set in your `Gemfile`.

  ```shell
  bundle exec jekyll serve
  ```

- deployment by 3rd party like GitHub Pages, Note that GitHub Pages runs in `safe` mode and only allows [a set of whitelisted plugins](https://help.github.com/articles/configuring-jekyll-plugins/#default-plugins).

  To use the currently-deployed version of the gem in your project, add the following to your `Gemfile`:

  ```
  source "https://rubygems.org"
  
  gem "github-pages", group: :jekyll_plugins
  ```

  Be sure to run `bundle update` often.



### very beginning of local Jekyll

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

        ```shell
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





### key points about Jekyll theme

- https://help.github.com/en/articles/customizing-css-and-html-in-your-jekyll-theme
- 





## LICENSE

- All Rights Reserved. Mostly, as GPL3.0.

- [LICENSE](LICENSE)

