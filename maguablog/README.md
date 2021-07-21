# Directory Structure

- **maguablog**  
    |---archetypes/ &emsp;&emsp;&emsp;&emsp; 放模板  
    |---content/ &emsp;&emsp;&emsp;&emsp;&emsp;&ensp; 放文章  
    &emsp;|---draft/      
    &emsp;|---post/  
    |---data/  
    |---layout/  
    |---public/ &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp; 放render完的東西(**[Magua's Adventure](https://sheeeep914.github.io/)**)  
    |---resources/  
    |---static/  
    &emsp;|---images/ &emsp;&emsp;&emsp;&emsp;&emsp; 放圖片(封面、個人主頁)  
    |---themes/  
    &emsp;|---tranquilpeak/  
    |---comfig.toml  
    |---README.md  

---

# How does the blog work?

- Add a post
``` bash
$ hugo new post/my-first-post.md
#this will render a post named "My First Post" in the content/post/ directory
```

- Add a draft 
``` bash
$ hugo new draft/my-first-draft.md
#this will render a post named "My First Post" in the content/draft/ directory
```

> ***NOTE:***  Draft will not be shown on the webpage! 

---

# Dealing with git 
Since we add a submodule(the actual webpage) to this dir, whenever the content is changed, there are several steps that must be followed in order to render the page successfully.

- Build the code 
    - `hugo -t tranquilpeak`
    - this will render everthing in the **./public** directory


- In the **./public** directory (under the **main** branch of repository **[sheeeep914.github.io](https://github.com/sheeeep914/sheeeep914.github.io.git)**)
    - `git add .`
    - `git commit -m "submodule add sth...."`
    - `git push origin main`

- Out in the root directory (under the **master** branch of repository **[hugo_blog](https://github.com/sheeeep914/hugo_blog.git)**)
    - `git add .`
    - `git commit -m "add sth...."`
    - `git push origin master`