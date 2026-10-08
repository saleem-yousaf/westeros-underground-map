# westeros-underground-map: corrected index.html (pivot menu fix)

REPLACE /index.html in the westeros-underground-map repo with this file, then
hard-refresh (GitHub Pages caches; also bypass the browser cache with
Ctrl+Shift+R, or load the page with ?v=2 once).

## Why the widget was missing
The widget code was correct, but the version live on the site was the old
index.html without the <script src="/builds-nav.js"> include. westeros's own
footer-fixer script runs either way, so the footer looked the same and hid the
fact that the include was not deployed.

## What this file has
- The /builds-nav.js include, last thing before </body> (this is what renders
  the top-right Builds menu).
- The canonical, author and JSON-LD meta (unchanged from before).
- The redundant extra footer I had added is removed; westeros keeps its own
  footer, which already backlinks to saleemyousaf.co.uk.

## Confirm after deploy
On the live page, DevTools Console:  window.__buildsNav   should return true,
and  document.querySelector('#bn-root')  should return the menu element.
