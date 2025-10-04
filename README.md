The navigation and footer fragments have been combined into `nav-footer.html`. Pages now fetch that file and extract the `<nav>` and `.footer` elements to inject into `#site-nav` and `#site-footer` respectively.

If you edit the site's menu or footer, update `nav-footer.html` once and the changes will appear across all pages after refresh.
