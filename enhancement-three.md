---
layout: default
title: Enhancement Three Demo
---

<h1>Enhancement Three: Corner Grocer App Demo</h1>

<p>This is a live demo of my Corner Grocer application, rewritten in Python and backed by SQLite.  You can sort items, search frequencies, and see the results update in real time.</p>

<div class="app-container">
  <iframe
    src="https://replit.com/@alyshaspradlin/CornerGrocer?embed=true"
    class="embedded-app"
    title="Corner Grocer Demo">
  </iframe>
</div>

<style>
/* you can also move these into your main CSS file if you prefer */
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
