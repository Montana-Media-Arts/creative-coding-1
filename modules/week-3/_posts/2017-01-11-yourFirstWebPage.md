---
title: Your First Web Page
module: 3
---
# Your First Web Page
Now that you know the basics of HTML it is time to write an HTML document and get it up on the web!

## 1: Create an HTML document
In your `/341-work` directory, create a new child directory labeled `/week-03-hw`.

Within that directory create a new html document labeled `index.html`. (NOTE: The `tree` command is used in the below images as an example. macOS users would need to install a separate script via homebrew to use this command. In other words, you are not expected to use tree. It is simply for demonstration purposes. All other commands however will work and should be used.)
![Showing the creation of index.html in the terminal.app](../imgs/addIndexHTML.png "Showing the creation of index.html in the terminal.app (macOS)")
![Showing the creation of index.html in the poweshell](../imgs/addIndexHTML_PC.png "Showing the creation of index.html in the PowerShell (windows)")

## 2: Open the file
Open the new file in your text editor. If you simply double-click the file, it will likely open in your default browser. Instead, you should do one of the following to open this file and its parent directory;

1. Drag the file to the icon of your text editor app from finder (macOS only).
2. Type `atom .` in terminal or powershell. (This assumes you have installed the "command line tools on mac" or installed atom as an admin for windows.)
3. Right-click the file in finder or explorer and select "open with". Then select your text editor (atom).

## 3: Create a Basic Document
If the file itself did not open it, click it from the side bar of the atom window. Now that this blank `index.html` document is in front of you, we need to fill it in.

### i. doctype declaration
Add the HTML5 doctype declaration on line 1. (Remember this must go in line 1. Nothing should be placed above the doctype declaration.)

<div id="code-heading">HTML</div>

{% highlight html linenos %}
<!DOCTYPE html>
{% endhighlight %}

### ii.  Fill in the Basic Structure
Add the basic structure elements (`<html>`, `<head>`, & `<body>`), starting in line 2. Also include the `utf-8` charset declaration and `title` elements in the head.

<div id="code-heading">HTML</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>

    </body>
</html>
{% endhighlight %}


### iii. Add a Page Title
Now you can start adding information to your page. First, you should add a title for the page. For the time being, let's make that “My First Web Page” by typing that between the title element tags on line 5.

<div id="code-heading">HTML</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>My First Web Page</title>
    </head>
    <body>

    </body>
</html>
{% endhighlight %}


### iv. Add Some Content!
Finally, add a `h1` element and two `p` elements. Populate these elements with your name, and the statement “Hello World!”, respectively.

<div id="code-heading">HTML</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>My First Web Page</title>
    </head>
    <body>
        <h1>Michael Musick</h1>
        <p>Hello World!</p>
    </body>
</html>
{% endhighlight %}


### v. Open the File in a Browser
OK, time to view your first webpage! You have a few options to open this file;

1. Double click the `index.html` file, as this should open the file in your default web-browser.
2. From terminal/powershell type `open index.html` (This should accomplish the same as above).
3. Drag the file to the browser you want it to open in.
4. Install the "open-in-browser" package for Atom and then either press `cntrl` + `opt` + `q` (macOS), `cntrl` + `alt` + `q` (PC), or from the command palate type "Open in Browser".

You should now see your file open in a web browser, looking something like this.
![Example of the first web page](../imgs/firstWebPage.png)

### vi. Make Some Changes
Back in your index.html document, add a new line before 10. There you should add a new paragraph element that includes the following text;

<div id="code-heading">HTML</div>
``` html
<p>This is my <em>first</em> web page!!!</p>
```


Your code should look like the following;

<div id="code-heading">HTML</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>
        <h1>Michael Musick</h1>
        <p>Hello World!</p>
        <p>This is my <em>first</em> web page!!!</p>
    </body>
</html>
{% endhighlight %}


### vii. Refresh the Page
Next, navigate back to your browser and refresh your web page (`cmd` + `r` [macOS], `cntrl` + `r` [windows]). You should see the update in your code reflected in the browser.
![Example of updating a web page](../imgs/firstWebPage2.png)
