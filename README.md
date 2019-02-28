<h2>How to use your own domain for github page?</h2>
<a href="https://www.youtube.com/watch?v=sTBY0D4gLg4" target="_blank">View my tutorials video here!</a>
<br><br><br>
<h2>How to use this template?</h2>
You can fork this project to your own project. <br>
Ex: fork and rename this repository to "yourname", you'll get the following address: yourusername.github.io/yourname
<br>Or clone it to your local (by using gitGUI or from cmd line), modify something and push from local to your account. <br>
<h2>How to change my title and something else? </h2>
Go to <b>_config.yml</b> file and change to what you want, you can add some social account to your profile view.

<h2>How to create new posts ?</h2>
create new file in <b>_posts</b> folder, the name of the file should be begin with "yyyy-mm-dd" and separated by "-" (dash) and end with ".md" (markdown format). Ex: "2015-05-12-documents.md" <br>
In the beginning of the content, copy and paste following:

```
--- 
layout: post
title:
description: "abcd"
modified: 2014-12-23
tags: [abc, def]
---
```

<br>
change your title, tag, modified date time...

<br>
<h2>How to post code?</h2>
use: <br>

```
{% highlight css %}
{% endhighlight %}
```

<br>
you can change "css" to some other languages such as cpp, java, html...
<br>
<br>
<h2>How to add or change menu on the left side? </h2>
Go to <b> _includes/navigation.html </b>

<h2>How to change color or anything else in the fixed navigation bar at the top? </h2>
Go to <b>_includes/head.html</b>

<h2>How about the background color?</h2>
Go to <b>_sass/_page.scss</b>
