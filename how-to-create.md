Steps to Create/Update this Rip
===============================

These steps are here primarily for Eric to use in the creation and updating of this theme.  Knowing what has been removed from the "standard" page will also assist in bug tracking.

1. Go to: http://ericjohnpc.nmu.edu/node/294
2. Run: `drush vset preprocess_css 0 --yes; drush vset preprocess_js 0 --yes`
3. Copy source
4. Run: `drush vset preprocess_css 1 --yes; drush vset preprocess_js 1 --yes`
5. Paste the source into BBEdit.  Do: Markup > Utilities > Format... > Pretty Print.  This should result in 377 lines.
6. Find and replace: `src="/sites`  >>  `src="//www.nmu.edu/sites`
7. Find and replace (grep): `@import url\("(.*?)\?xxxxxx"\);`  >>  `<link type="text/css" rel="stylesheet" href="\1" media="all" />`  
  >where xxxxxx is the cache salt
8. Find and replace: `<a href="/` >> `<a href="//www.nmu.edu/`
9. Find and replace: `http://www.nmu.edu` >>  `//www.nmu.edu`
10. Find and replace (grep): `<style type="text/css" media="all">|</style>` >>  `[nothing]`
11. Find (grep): `<style type="text/css" media=".*?">`  
  >Manually replace the media property for child elements of the style tag found above.  Remove those media elements when done.
13. Find and replace: `?xxxxxx` >>  `[nothing]`
  >where xxxxxx is the cache salt
14. Remove the jquery.extend settings
15. Remove omega-mediaqueries.js
16. Remove panels.js
17. Remove google\_analytics\_reports.js
18. Remove drupal.js
19. Remove jquery.once.js
20. Remove all /system/ and /modules/ CSS files
21. Remove shortlink tag
22. Remove mega generator tag
23. Remove canonical tag
24. Remove skip-link div
25. Add Comments for easy finding: page title, page branding, top navigation and page content.
26. Add google analytics tracking code from profile UA-27629684-6.
