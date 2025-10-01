Shared navbar
===============

This folder uses a single shared navigation fragment so updates to the site menu apply to all pages.

How it works
------------

- The shared navbar is `navbar.html` and contains the site's <nav> markup.
- Each page includes it by placing a placeholder element (for example `<div id="site-nav"></div>`) and running a small script that fetches `navbar.html` and injects the HTML.

Example (already used in the pages):

```html
<div id="site-nav">Loading navigation...</div>
<script>
    fetch('navbar.html')
        .then(resp => { if (!resp.ok) throw new Error('Network response was not ok'); return resp.text(); })
        .then(html => document.getElementById('site-nav').innerHTML = html)
        .catch(err => { document.getElementById('site-nav').innerText = 'Failed to load navigation.'; console.error(err); });
</script>
```

Notes
-----

- `navbar.html` is referenced relative to each page inside the `HTMLpages/` folder, so keep it in this folder.
- Styles are loaded from `../Styles/styles.css` in the pages; no change is required for CSS to apply to the injected navbar.
- If you later move pages to a different folder, update the fetch path or use an absolute path (for example `/HTMLpages/navbar.html`).
