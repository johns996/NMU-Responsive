NMU-Responsive
==============

This is a non-Drupal version of the Responsive NMU theme. It is basicly a source rip and conversion from the current site.  These template files were created to allow pages/sites outside of Drupal to use an "offical" version of the responsive theme. 

This repository is managed by Eric Johnson in the Communications and Marketing office.  Updates made to any of the theme-level elements on the main NMU site will be duplicated here.  Questions about using this template or feature requests can be sent to ericjohn@nmu.edu.

Steps to Create/Update this Rip
-------------------------------

1. Go to: http://ericjohnpc.nmu.edu/node/294
2. Run: drush vset preprocess_css 0 --yes; drush vset preprocess_js 0 --yes
3. Copy source
4. Run: drush vset preprocess_css 1 --yes; drush vset preprocess_js 1 --yes
5. Paste the source into BBEdit.  Do: Markup > Utalities > Format... > Pretty Print.  This should result in 377 lines.
6. Find and replace: src="/sites  >>  src="//www.nmu.edu/sites
7. Find and replace (grep): @import url\("(.*?)\?xxxxxx"\);  >>  <link type="text/css" rel="stylesheet" href="\1" media="all" />
8. Find and replace: <a href="/ >> <a href="//www.nmu.edu/
9. Find and replace: http://www.nmu.edu >>  //www.nmu.edu
10. Find and replace (grep): <style type="text/css" media="all">|</style> >>  [nothing]
11. Find (grep): <style type="text/css" media=".*?">
12. Manually replace the media property for child elements of the style tag found above.  Remove those media elements when done.
13. Find and replace: ?xxxxxx >>  [nothing]
14. Remove the jquery.extend settings
15. Remove omega-mediaqueries.js
16. Remove panels.js
17. Remove google_analytics_reports.js
18. Remove drupal.js
19. Remove jquery.once.js
20. Remove all /system/ and /modules/ CSS files
21. Remove shortlink tag
22. Remove mega generator tag
23. Remove canonical tag
24. Remove skip-link div
25. Add Comments for easy finding: page title, page branding, top navigation and page content.  
