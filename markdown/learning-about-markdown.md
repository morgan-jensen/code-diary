# Learning About Markdown

##### **Questions I Have**
* Is markdown tracked by git? And if so, how well?
* Why should I use it?

##### **Answers**

_Is markdown tracked by git?_
I originally tried to just google the answer, but I just got a bunch of links to tutorials for adding a markdown README to your git repo. Luckily for me, it is easy enough to test for myself. 

I made a quick repository on my local machine and added a markdown file called **`test.md`**. I then made the initial commit to make sure tht the empty file was commited to the repository. 

I then added some simple changes like so:
```
# This is a test to see if git can track markdown

These lines should show as changes in the repo
```

Upon calling 'git status', I noticed that it showed changes in the markdown file. This lead me to believe that it is tracked by git. However, I wanted to know if it could keep track of the changes in the file, or if it just knows that something about the file has changed. Upon inspection with Git GUI, I was able to see the differences between the initial and new commits in the file. Just to be sure, I repeated the process, adding a few lines and deleting one to see if I could view the changes. Git showed me all the changes correctly.

Conclusion: Git tracks markdown at least as well as it does something like HTML.

_Why should I use it?_

From: [UltraEdit.com](https://ultraedit.com/company/blog/community/what-is-markdown-why-use-it.html)
* It's easy to learn and fast to use
	* It has been easy so far from my personal experience
* It converts to html easily
	* Excelent for readme files 
	* MD is essentially a text-to-HTML converter
* Markdown is future proof
	* MD is plain text, so it will be supported as long as plain text is supported (long time)
* It's used everywhere
	* Unofficial standard for sites like GitHub
	* Default formatting option for apps like Skyhpe, Slack, and to some extent, Facebook Messenger
	

* Upon pushing this to github, I also realize that it makes it really easy to see and edit on github. Almost like the repository is a real diary.
