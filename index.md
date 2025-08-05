---
layout: default
title: Software Development ePortfolio
---

<h1 id="typed-text">Welcome to My Software Development ePortfolio</h1>

<div class="intro-text">
  This is my Software Development ePortfolio site. Here you will find the projects and enhancements I have created while working toward my CS bachelor's in Software Development.
</div>

<!-- Terminal Window: Code Review -->
<div class="terminal-window">
  <div class="terminal-header">
    <span>Code Review</span>
    <div class="terminal-buttons">
      <div class="terminal-button minimize"><i class="fa-solid fa-window-minimize"></i></div>
      <div class="terminal-button maximize"><i class="fa-regular fa-window-maximize"></i></div>
      <div class="terminal-button close"><i class="fa-solid fa-x"></i></div>
    </div>
  </div>
  <div class="terminal-content">
    <code>
apursley2012@ePortfolio-PC:~$ cd software-development-e-portfolio  
apursley2012@ePortfolio-PC:~/software-development-e-portfolio$ python  
Python 3.11.4 (tags/v3.11.4)  
&gt;&gt;&gt; # Open and read Code Review page  
&gt;&gt;&gt; path = r"software-development-e-portfolio/code-review.md"  
&gt;&gt;&gt; file = open(path, "r")  
&gt;&gt;&gt; print(file.read())  
Opening file: code-review.md ...  
<span class="clickable-link" onclick="openPage('code-review')">code-review.md</span>
    </code>
  </div>
  <div class="status-bar">Ready</div>
</div>

<!-- Repeat for Enhancements 1–3 -->
<div class="terminal-window">
  <div class="terminal-header">
    <span>Enhancement One: CornerGrocer App</span>
    <div class="terminal-buttons">
      <div class="terminal-button minimize"><i class="fa-solid fa-window-minimize"></i></div>
      <div class="terminal-button maximize"><i class="fa-regular fa-window-maximize"></i></div>
      <div class="terminal-button close"><i class="fa-solid fa-x"></i></div>
    </div>
  </div>
  <div class="terminal-content">
    <code>
apursley2012@ePortfolio-PC:~$ cd software-development-e-portfolio  
apursley2012@ePortfolio-PC:~/software-development-e-portfolio$ python  
Python 3.11.4 (tags/v3.11.4)  
&gt;&gt;&gt; # Open and read Enhancement One  
&gt;&gt;&gt; path = r"software-development-e-portfolio/enhancement-one.md"  
&gt;&gt;&gt; file = open(path, "r")  
&gt;&gt;&gt; print(file.read())  
Opening file: enhancement-one.md ...  
<span class="clickable-link" onclick="openPage('enhancement-one')">enhancement-one.md</span>
    </code>
  </div>
  <div class="status-bar">Ready</div>
</div>

<div class="terminal-window">
  <div class="terminal-header">
    <span>Enhancement Two: Sort & Search</span>
    <div class="terminal-buttons">
      <div class="terminal-button minimize"><i class="fa-solid fa-window-minimize"></i></div>
      <div class="terminal-button maximize"><i class="fa-regular fa-window-maximize"></i></div>
      <div class="terminal-button close"><i class="fa-solid fa-x"></i></div>
    </div>
  </div>
  <div class="terminal-content">
    <code>
apursley2012@ePortfolio-PC:~$ cd software-development-e-portfolio  
apursley2012@ePortfolio-PC:~/software-development-e-portfolio$ python  
Python 3.11.4 (tags/v3.11.4)  
&gt;&gt;&gt; # Open and read Enhancement Two  
&gt;&gt;&gt; path = r"software-development-e-portfolio/enhancement-two.md"  
&gt;&gt;&gt; file = open(path, "r")  
&gt;&gt;&gt; print(file.read())  
Opening file: enhancement-two.md ...  
<span class="clickable-link" onclick="openPage('enhancement-two')">enhancement-two.md</span>
    </code>
  </div>
  <div class="status-bar">Ready</div>
</div>

<div class="terminal-window">
  <div class="terminal-header">
    <span>Enhancement Three: SQLite DB</span>
    <div class="terminal-buttons">
      <div class="terminal-button minimize"><i class="fa-solid fa-window-minimize"></i></div>
      <div class="terminal-button maximize"><i class="fa-regular fa-window-maximize"></i></div>
      <div class="terminal-button close"><i class="fa-solid fa-x"></i></div>
    </div>
  </div>
  <div class="terminal-content">
    <code>
apursley2012@ePortfolio-PC:~$ cd software-development-e-portfolio  
apursley2012@ePortfolio-PC:~/software-development-e-portfolio$ python  
Python 3.11.4 (tags/v3.11.4)  
&gt;&gt;&gt; # Open and read Enhancement Three  
&gt;&gt;&gt; path = r"software-development-e-portfolio/enhancement-three.md"  
&gt;&gt;&gt; file = open(path, "r")  
&gt;&gt;&gt; print(file.read())  
Opening file: enhancement-three.md ...  
<span class="clickable-link" onclick="openPage('enhancement-three')">enhancement-three.md</span>
    </code>
  </div>
  <div class="status-bar">Ready</div>
</div>

<script>
function openPage(pageName) {
  window.location.href = pageName + '.html';
}
</script>
