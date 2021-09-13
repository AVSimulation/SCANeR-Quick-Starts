# Pages Edition Manual

## 1. Good practices

* Follow the file tree below
* New pages go into ```(root)/Pages/(page_title).md```
* Images go into ```(root)/Pages/assets/```
* Avoid blank spaces in folder or file names, as they require '\%20' when referenced in markdown
* Reference new pages in ```(root)/index.md```

![](./assets/PagesFileTree.PNG)

### Links

Links between articles can use relative paths.  
`[How to download the Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`
[How to download the Trial version of SCANeR](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)

At the beginning of the article, add links to the articles with informations necessary prior.  
`:arrow_left: [How to download the Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
:arrow_left: [How to download the Trial version of SCANeR](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)

At the end of the article, add links to the articles that may interest the reader after.  
`:arrow_right: [How to download the Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)`  
:arrow_right: [How to download the Trial version of SCANeR](./Pages/HT_Download_Trial_SCANeR/HT_Download_Trial_SCANeR.md)

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
https://github.com/AVSGuillaume/Samples-Pack/tree/Pages

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
git remote add origin https://github.com/AVSGuillaume/Samples-Pack.git
git fetch origin Pages
```
* When prompted, login to GitHub with the account linked to your company e-mail.
* Once fetching is finished, run the following command in the Git Bash console
```
git checkout Pages
```
This creates a new local branch "Pages" that with upstream "origin/Pages"
Now your working tree has the latest version of the Pages files.

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
