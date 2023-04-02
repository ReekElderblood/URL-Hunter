# Script-Scraper
Check out this JavaScript code that extracts URLs from a web page and linked scripts! Perfect for web scraping and penetration testing

## How to use:
1. Open a web page you want to extract URLs from.
2. Open the developer console by pressing Ctrl + Shift + J on Windows or Cmd + Option + J on Mac.
3. Paste the following code into the console and press enter:
  ```js
javascript:(function(){var scripts=document.getElementsByTagName("script"),regex=/(?<=(\"|\'|\`))\/[a-zA-Z0-9_?&=\/\-\#\.]*(?=(\"|\'|\`))/g;const results=new Set;for(var i=0;i<scripts.length;i++){var t=scripts[i].src;""!=t&&fetch(t).then(function(t){return t.text()}).then(function(t){var e=t.matchAll(regex);for(let r of e)results.add(r[0])}).catch(function(t){console.log("An error occurred: ",t)})}var pageContent=document.documentElement.outerHTML,matches=pageContent.matchAll(regex);for(const match of matches)results.add(match[0]);function writeResults(){results.forEach(function(t){document.write(t+"<br>")})}setTimeout(writeResults,3e3);})();
  ````
4. Wait for the script to finish running. The extracted URLs will be displayed in the console.

