%%%%%%%
% Slide Show Headers

title: Create Mobile Web Apps with the iUI JavaScript Library
gradient: top_bottom blue navy


%%%%%%%%%%%%%
% Slides Start Here

# Create Mobile Web Apps with the iUI JavaScript Library 

[Gerald Bauer](http://geraldbauer.ca) @ [MobileCampVancouver2](http://barcamp.org/MobileCampVancouver2), Vancouver, British Columbia, September 2008



# What's the Mobile Web?

The mobile web is just like the regular web but you access it on the go using mobile devices 
such as mobile phones, mobile music/media players, mobile internet tablets etcetera.

Related Terms:

"One Web" -  Before the Apple iPhone popularized the mobile web
the industry used different "standards" 
for web access on mobile devices such as Wireless Markup Language (WML) 
or Wireless Access Protocoll (WAP) or XHTML Basic.

One Web =  Use "classic" HTML, CSS, JavaScript, etcetera on the mobile web.
No need for different "standards".


# Why does the mobile web matter?

* Billions of mobile phones. 
* More and more "smart" phones have built-in industry-strength browsers.


# How does the mobile web differ from the "classic" web?

### Usually smaller screen

e.g. Apple's iPhone screen size is 320x480 pixel or 480x320 pixel.

Note, iPhone's browser lets you zoom in and zoom out. By default for non-mobile
web screen size optimized sites iPhone will zoom out 
to make the screen appear to have a size of 980 pixels (instead of the actual 320).

### Limited keyboard for text entry and limited clicking (no mouse)

Use accesskey for links allowing you to "click" links using your phone key numbers (
such as 1,2,3,4,5,etc.)

### Limited connectivity/offline

### Special links for phone numbers

```
<a href="tel:1-604-555-5555">1-604-555-5555</a>
```


# What's iUI?

iUI is an open-source framework (really just one `iui.js` - JavaScript file,
one `iui.css` - style sheet and many graphics)
created by Joe Hewitt (of Firebug fame) and now working at Facebook (and responsible for - surprise, surprise - the mobile web version of Facebook).

* [iUI Project Site](http://code.google.com/p/iui)
* [iUI Intro](http://www.joehewitt.com/blog/introducing_iui.php)  by Joe Hewitt  


# iUI Design

* Single-Page Web Application (Clicking on link fires off an Ajax/JavaScript request -> Page gets updated  w/ animation effect!)
* Ajax/JavaScript Machinery Hidden - Just use plain HTML list tags (`ul`, `li`), links (`a`) and it works; no JavaScript coding required.
* Back button still works.

# iUI - Getting Started in Three Minutes

Step 1: Download and Unzip iUI Package @ [code.google.com/p/iui](http://code.google.com/p/iui)

Step 2: Try the Music Example or the Theaters Search Example (Open Up Page in a WebKit Browser)

That's it. No Developer $$$ Fee. No F!?#!ing Non-Disclosure Agreement (NDA).


# iUI - Lists

![](i/iui-hoods.png)

```
<ul title="Neighbourhoods">               
  <li><a href='/hood/1'>Commercial Drive</a>
    <span class='small'>Eastside</span>
  </li>                 
  <li><a href='/hood/2'>Mount Pleasant</a>
    <span class='small'>Eastside</span>
  </li>                 
  <li><a href='/hood/3'>Kitsilano</a>
    <span class='small'>Westside</span>
  </li>                 
  <li><a href='/hood/4'>Yaletown</a>
    <span class='small'>Downtown</span>
  </li>                 
</ul>
```

(Source: [Roomienator](http://rubybook.ca/2008/02/12/iui))


# iUI - Groups and Lists

![](i/iui-home.png)

```
<ul title="RoomieNATOR" selected="true">

  <li class="group">Browse</li>
    <li><a href='/neighbourhoods'>Neighbourhoods</a></li>
    <li><a href='/posts'>Posts</a></li>

  <li class="group">Accounts</li>
    <li><a href='/login'>Login</a></li>
    <li><a href='/signup'>Sign up</a></li>

  <li class="group">About</li>
    <li><a href="#help">Help</a></li>
    <li><a href="#about">About</a></li>
</ul>
```

Add `class='group'` to mark list item for grouping. That's it.

# iUI - Panels

![](i/iui-panel.png)

```
<div id="about" title="About" class="panel">
  <h2>About RoomieNATOR</h2>
  <p>Sample Mobile Web App using the iUI JavaScript Library w/ Ruby on Rails</p>
</div>
```

Add `class='panel'` to mark `div` block as a panel. That's it.

# iUI - Link Types

* Intra-Page iUI Link (`#artists`)
* iUI Link  (`/stats`)
* Plain Old Link (Reload New Page) (`target='_self'`)

![](i/iui-links.png)

```
<ul id="home" title="Music" selected="true">
  <li><a href="#artists">Artists</a></li>
  <li><a href="#settings">Settings</a></li>
  <li><a href="/stats">Stats</a></li>
  <li><a href="http://code.google.com/p/iui/" target="_self">About</a></li>
  <li>Nothing</li>
</ul>
```

# Intra-Page iUI Links

Browse Lists and Pages without Network Access

```
<ul id="artists" title="Artists">
  <li class="group">B</li>
    <li><a href="#TheBeatles">The Beatles</a></li>
    <li><a href="#BelleSebastian">Belle & Sebastian</a></li>
  <li class="group">C</li>
    <li><a href="#CrowdedHouse">Crowded House</a></li>
</ul>
<ul id="TheBeatles" title="The Beatles">
  <li><a href="#songs">Abbey Road</a></li>
  <li><a href="#songs">Help!</a></li>
  <li><a href="#songs">Rubber Soul</a></li>
  <li><a href="#songs">Sgt. Pepper's</a></li>
  <li><a href="#songs">White Album</a></li>
</ul>
<ul id="BelleSebastian" title="Belle & Sebastian">
  <li><a href="#songs">Boy With The Arab Strap</a></li>
  <li><a href="#songs">Dear Catastrophe Waitress</a></li>
  <li><a href="#songs">The Life Pursuit</a></li>
</ul>
...
```

# iUI - Forms

![](i/iui-form.png)

```
<form title="Login" class="panel" action="/login" method="POST">

<h2>Welcome to RoomieNATOR</h2>

<fieldset>
  <div class="row">
    <label>Name</label>
    <input type="text" name="login" value="<%%= params[:login] %>" >
  </div>
  <div class="row">
    <label>Password</label>
    <input type="password" name="password" value="<%%= params[:password] %>" >
  </div>
</fieldset>
<a class="whiteButton" type="submit" href="#">Login</a>
</form>
```

Mark `div` block with `class='row'` for form rows and submit button with `class='whiteButton'`.


# All Together Now

* Single-Page Web Application (Clicking on link fires off an Ajax/JavaScript request -> Page gets updated  w/ animation effect)

```
<html>
  <head>
    <title>RoomieNATOR</title>
    
    <style>@import "/iui/iui.css";</style>
    <script src="/iui/iui.js"></script>
  </head>
  <body>
    <div class="toolbar">
      <h1 id="pageTitle"></h1>
      <a id="backButton" class="button" href="#"></a>
      <a class="button" href="#searchForm">Search</a>
    </div>

    <%%= yield %>

  </body>
</html>
```

* Include iUI Style Sheet
* Include iUI JavaScript Library
* Setup Toolbar with Back Button and Search Button

That's it.

# iUI - Lists and Ruby 

![](i/iui-hoods.png)

```
<ul title="Neighbourhoods">               
  <%% for hood in @neighbourhoods do %>
    <li><%%= link_to hood.name, hood %>
     <span class='small'> <%%= hood.area %></span>
    </li>                 
  <%% end %>
</ul>
```

Generates

```
<ul title="Neighbourhoods">               
  <li><a href='/hood/1'>Commercial Drive</a>
    <span class='small'>Eastside</span>
  </li>                 
  <li><a href='/hood/2'>Mount Pleasant</a>
    <span class='small'>Eastside</span>
  </li>                 
  <li><a href='/hood/3'>Kitsilano</a>
    <span class='small'>Westside</span>
  </li>                 
  <li><a href='/hood/4'>Yaletown</a>
    <span class='small'>Downtown</span>
  </li>                 
</ul>
```


# Alternatives

* CiUI (CNet iUI)
  * [Project Site](http://code.google.com/p/ciui-dev)
  * [CNET Example](http://iphone.cnet.com)

and others

![](i/ciui.png)


# The Browser Players - WebKit, WebKit, WebKit

Good news. Microsoft's Internet Explorer Web Browser is an also ran.

The defacto industry standard are browsers using the open source WebKit browser kernel/engine.

Mobile browsers built on WebKit include:

* Apple's iPhone/iPod Safari 
* Nokia Symbian 60 (S60) Series Web Browser
* Google's Android

Other mobile browser include:

* Opera Mini/Mobile
* Microsoft Internet Explorer Mobile
* Mozilla Firefox Mobile (Fennec) (Open Source)


# Browser Innovation in WebKit

* Better & More Web Markup Functionality (HTML5)
  * more form functionality (datepickers, required, repeat, etc.)
  * standard audio, video tags 
  * new tags such as header, footer, nav, aside, figure, dialog, m (mark), time, meter, progress 
  * much more

<!-- -->

* Better & More Scripting Functionality (JavaScript)
  * 2D & 3D graphics using JavaScript (Canvas) built into browser (no Flash plugin required!)
  * standard HTTP request service (also known as Ajax)
  * offline storage 
  * much more

<!-- -->

* Better & More Cascading Style Stylesheet Functionality
  * rounded borders, animation, etc.
  * much more


# About Web Kit

History/Beginnings:

Konqueror - Linux KDE Desktop Browser - Tagline: A Lean, Mean Web Browser

Building Blocks: KHTML, KJS

Instead of building the browser for the Apple OS X
from scratch Apple decides to build on/reuse the open source KHTML/KJS core.

* [Web Kit Open Source Project Site](http://webkit.org)
* [Planet Web Kit](http://planet.webkit.org)

Desktop Browsers Using WebKit

* Apple Safari
* Google Chrome/Chromium
* Adobe Integrated Runtime (AIR)
* Linux KDE Browser


# More Mobile Web Links

* [Official W3C Mobile Web Site](http://w3.org/Mobile)
* [Official W3C Mobile Web Best Practices](http://w3.org/TR/mobile-bp)
* [Planet Mobile Web](http://w3.org/Mobile/planet)

# That's It. Thank You.

