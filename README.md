# Articles Edition Manual

## 1. Good practices

* Follow the file tree below
* New pages go into ```(root)/Pages/(page_title).md```
* Images go into ```(root)/Pages/assets/```
* Avoid blank spaces in folder or file names, as they require '\%20' when referenced in markdown
* Reference new pages in ```(root)/index.md```
```
📄 index.md
📁 Pages/
↳ 📁 ...
  📁 HT Download Trial/
  ↳ 📄 HT Download Trial.md
    📄 ...
    📁 Assets/
    ↳ 🖼️ image.jpg
      🎞️ video.avi
      🖼️ ...
```

### Header

Each page markdown can have a header:
```
---
group: Get Ready
short: Download the Trial
order: 10
---
```
* `group` is the collection of guides this page belongs to ("Get Ready", "Get Started", etc...)
  > * For each page of a group, the navigation box appears on the left and lists all member pages.  
  > * The :arrow_left: "previous page" and :arrow_right: "next page" links are automatically created within a group.
* `short` is the title of the article.
  > This is the title used in the navigation box, and "previous/next" links.
* `order` is the position of the guide in the group.
  > Advised to go by increments of 10, so it's easier to insert pages later (with `order: 15` for example)

* The last page of a group has a "next" link to the first page of the next group.
* The first page of a group has a "prev" link to the last page of the previous group.
The groups order is defined in `_config.yml`.

> The header is optional, but without it the navigation box and previous/next links will not appear.

### Links

Links between articles can use relative paths.  
`[Download the Trial](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
[Download the Trial](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)

Suggest another article with the hook icon:  
`:leftwards_arrow_with_hook: [Download the Trial](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
:leftwards_arrow_with_hook: [Download the Trial](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)

Manual previous/next links (in case your page is not in a group):  
`:arrow_left: [Download the Trial](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
:arrow_left: [Download the Trial](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)  
`:arrow_right: [Download the Trial](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
:arrow_right: [Download the Trial](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)  

### Videos

Don't push videos onto the repository itself. It is too heavy.

Youtube videos can be embedded in the article.  
On the Youtube page of the video:
* Button "Share"
* Icon "Embed"
* Copy the html code provided
* Paste as is in the markdown article

```<iframe width="560" height="315" src="https://www.youtube.com/embed/ldsQqeoovZU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>```

## 2. Using GitHub web editor

The GitHub interface includes the necessary editors.  
https://github.com/AVSimulation/SCANeR-Quick-Starts/tree/Published

### Markdown editor

```Add file > Create new file```

Set the file name with ```.md``` extention to activate syntax colouring, and correct result in the ```Preview``` tab.  
In the file name, add a ```/``` to create a new folder

### Upload images

```Add file > Upload files```  

To create the ```assets``` folder, create a new file called ```folder/deleteme```  
Then delete the ```deleteme``` file and upload your images in it.

## 3. Using a local Git repo

### Set up the Git local repo

* Navigate inside folder dedicated to Pages edition (e.g. D:/Pages/)
* `Right click > Git Bash here`
* In the Git Bash console, run the following commands
```
git init
git remote add origin https://github.com/AVSimulation/SCANeR-Used-Guides.git
git fetch origin Published
```
* When prompted, login to GitHub with the account linked to your company e-mail.
* Once fetching is finished, run the following command in the Git Bash console
```
git checkout Published
```
This creates a new local branch "Published" that with upstream "origin/Pages"
Now your working tree has the latest version of the website files.

### Publish a modification

#### Get the latest version from GitHub

```
git pull
```

#### Start working
 
```
git status
```
```
git add Pages/HT_Something/*
```
```
git commit -m "Created or modified some page"
```

#### Publish your modifications

```
git push
```
