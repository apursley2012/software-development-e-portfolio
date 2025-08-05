---
layout: default
title: Enhancement Two Demo
---

<h2>Corner Grocer App – Enhancement Two (Interactive Demo)</h2>

<div class="terminal-window">
  <div class="terminal-header">
    <span>Corner Grocer Demo (Enhancement 2)</span>
  </div>
  <div class="terminal-content">
    <!-- User input area -->
    <textarea id="item-input" placeholder="Enter one item per line…&#10;Spinach&#10;Radishes&#10;Broccoli"></textarea>

    <!-- Controls -->
    <div class="controls">
      <label>Lookup: <input id="lookup-item" placeholder="e.g. apples"></label>
      <button id="btn-lookup">Lookup</button>
      <button id="btn-print-all">Print All</button>
      <button id="btn-histogram">Histogram</button>
      <button id="btn-sort-alpha">Sort A→Z</button>
      <button id="btn-sort-freq">Sort by Freq</button>
      <button id="btn-search">Search</button>
      <button id="btn-save-list">Download List</button>
      <button id="btn-save-hist">Download Histogram</button>
    </div>

    <!-- Output -->
    <pre id="output">[ paste your list above and click a button ]</pre>
  </div>
  <div class="status-bar">Ready</div>
</div>

<script src="https://cdn.jsdelivr.net/pyodide/v0.23.2/full/pyodide.js"></script>
<script>
  let pyodide, ready = false;
  async function boot() {
    pyodide = await loadPyodide();
    await pyodide.runPythonAsync(`
from collections import defaultdict
class GroceryFrequency:
    def __init__(self): self.freq = defaultdict(int)
    def process_text(self, text):
        self.freq.clear()
        for line in text.splitlines():
            it = line.strip().lower()
            if it: self.freq[it] += 1
    def lookup(self, item): return self.freq.get(item.lower(), 0)
    def all_freq(self): return dict(self.freq)
    def histogram(self): return {k: '*'*v for k,v in self.freq.items()}
def sort_alpha(d): return sorted(d.items(), key=lambda x:x[0])
def sort_by_freq(d): return sorted(d.items(), key=lambda x:x[1], reverse=True)
def search_item(d, it):
    it = it.lower()
    return (it, d[it]) if it in d else None

import js
js.GF = GroceryFrequency
js.sort_alpha = sort_alpha
js.sort_by_freq = sort_by_freq
js.search_item = search_item
    `);
    ready = true;
  }
  boot();

  function makeInstance() {
    const inst = pyodide.globals.get("GF")();
    inst.process_text(document.getElementById("item-input").value);
    return inst;
  }
  function setOut(txt) { document.getElementById("output").textContent = txt; }

  document.getElementById("btn-lookup").onclick = () => {
    if(!ready) return;
    const inst = makeInstance();
    const it = document.getElementById("lookup-item").value;
    setOut(`${it}: ${inst.lookup(it)}`);
  };
  document.getElementById("btn-print-all").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    let o = "";
    Object.keys(f).sort().forEach(k=> o+=`${k}: ${f[k]}\n`);
    setOut(o);
  };
  document.getElementById("btn-histogram").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), h = inst.histogram();
    let o = "";
    Object.keys(h).sort().forEach(k=> o+=`${k}: ${h[k]}\n`);
    setOut(o);
  };
  document.getElementById("btn-sort-alpha").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    const sa = pyodide.runPython("sort_alpha")(f).toJs();
    let o = "";
    sa.forEach(([k,v]) => o+=`${k}: ${v}\n`);
    setOut(o);
  };
  document.getElementById("btn-sort-freq").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    const sf = pyodide.runPython("sort_by_freq")(f).toJs();
    let o = "";
    sf.forEach(([k,v]) => o+=`${k}: ${v}\n`);
    setOut(o);
  };
  document.getElementById("btn-search").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    const it = document.getElementById("lookup-item").value;
    const r = pyodide.runPython("search_item")(f, it);
    if(r === null) setOut("Item not found.");
    else { let [k,v] = r.toJs(); setOut(`${k}: ${v}`) }
  };

  function download(name, text) {
    const b = new Blob([text],{type:"text/plain"});
    const u = URL.createObjectURL(b);
    const a = document.createElement("a");
    a.href=u; a.download=name; a.click();
    URL.revokeObjectURL(u);
  }
  document.getElementById("btn-save-list").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    let o="";
    Object.keys(f).sort().forEach(k=> o+=`${k} ${f[k]}\n`);
    download("frequency_list.txt", o);
  };
  document.getElementById("btn-save-hist").onclick = () => {
    if(!ready) return;
    const inst = makeInstance(), f = inst.all_freq();
    let arr = Object.entries(f).sort((a,b)=>b[1]-a[1]||a[0].localeCompare(b[0]));
    let o="";
    arr.forEach(([k,v])=> o+=`${k}: ${"*".repeat(v)}\n`);
    download("frequency_histogram.txt", o);
  };
</script>
