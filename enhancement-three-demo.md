---
layout: default
title: Enhancement Three Demo
---

<h1 id="typed-text">Corner Grocer App Demo</h1>

<p>This is a <b><em>simulated demonstration</em></b> of the Corner Grocer Enhancement 3, which connects the application to a SQLite database for persistent storage.
  <br>
Since GitHub Pages is a <b><em>static hosting service</em></b>, it can’t run an actual database or backend code in real time.  
  <br>
For this demo, the database interactions have been <b><em>mocked</em></b> so you can still explore the app’s functionality and see how the UI works as if it were connected to a real database.  
<br>
The original implementation **runs with a real SQLite database** when hosted in an environment that supports server-side processing.  
I wanted to showcase this in a way that took it from just a console app, to what feels and works like a real functional app. I think this demo accomplishes that well, even if it can't run the actual database part here on GitHub.</p>

<div class="app-container" style="margin: 2rem 0; border-radius: 12px; overflow: hidden; box-shadow: 0 8px 32px rgba(0,0,0,0.12);">
  <iframe
    src="https://0d394c1a-e07e-4561-aa6f-dd80385df9db-00-loqi0vrnbdsb.spock.replit.dev/"
    class="embedded-app"
    title="Corner Grocer Demo"
    style="width:100%; height:800px; border:none; display:block;"
  ></iframe>
</div>



<style>
.app-container {
  margin: 2rem 0;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 8px 32px rgba(0,0,0,0.12);
}
.embedded-app {
  width: 100%;
  height: 800px;
  border: none;
  display: block;
}
@media (max-width: 768px) {
  .embedded-app {
    height: 600px;
  }
}
</style>
