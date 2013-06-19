NMU-Responsive: How To Use
==========================

This *template* is  just a boilerplate file to be used on pages and forms that can't be integrated in NMU's Drupal system.  It is designed to emulate the NMU-Responsive theme output so the markup may be a bit bloated in places but this is done to ensure that one set of styles can be used for the NMU site and any pages using this template.

It is **strongly** recommended that edits are only applied to the following regions:
-page title
--use this region to identify your pages in bookmarks and search engines.
--it should always follow the format: Page Name | Northern Michigan University
--or using the a department's name: Page Name | NMU Administrative Information Technology

-page branding
--use this region to identify the department associated with the content
--this region will also contain links back to the department's homepage and the university's homepage
--use the class **main_title** for the main page title
--use the class **sub_titles** for the department homepage link and the NMU link
--these classes are read by the page's javascript and used in the mobile layout
---there should only be one main title on any page
---only the first sub title element will be read and stored for the mobile home link

-top navigation
--use this region to provide top level navigation for the page.
--no classes are needed for this region.  simply put everything in an unsorted list.
--this navigation should reflect the associated department's top navigation
--navigation snippets for commonly used departments are stored in the **top_navigation** folder
--when creating custom navigation sets, the navigation should only take up a single line on the desktop-narrow view (960 px wide).  This is the layout that is one smaller than the widest layout.

-page content
--use this region for the main page content.
--use the guidelines below for formatting content for this region.


Page Content Formatting Guidelines
----------------------------------

###Tables###
Tables do not work well in mobile layouts and should never be used to layout content on a page.  If a page is presenting tabular data, then a table should be used but be aware that a mobile screen will shrink this table down to 320 pixels wide and very few tables look good at this width.

If you are putting content on a page that needs to have a table at a size larger than 320 pixels, wrap your table tags in a <div class="overflow-table">[...]</div>.  This div will allow a table to maintain it's original size and scroll to the right in mobile view.

Avoid putting images in tables whenever possible.  Images within tables are handled differently across all browsers since there is not a W3C specification for images in non-block-level elements.  If you do need to put an image in a table, be sure to test it in a mobile layout before deploying.

###Images###
As much as possible, limit the number and size of images on your pages.  Obviously some pages need to help make the presentation of the page appealing to a user.  However, each additional image added to a page will slow down the time it takes for a user to load that page, especially on a mobile device.

Never use images to represent something that could be conveyed with text.  If this must be done to achieve a certain design make sure that image contains alternative text.  Adding title's to images will also provide pop-up text on image mouseover.

`<img src="..." alt="Students Walking on Campus" title="Discover NMU" width="300" height"150" />`

Always resize an image to the dimensions it will be displayed at using an image resizing program.  Using the width/height tag to size an image will not change it's physical size, instead it will just shrink the image down in the browser window.  This will force the user to download more data than needed and subsequently slow down a user's web experience.

Images stored on the NMU server can be referenced using a protocol-agnostic method allowing them to be served up via http or https depending on the requesting connection.  This is done by omitting the *http:* or *https:* as demonstrated in the following example.

`<img src="//www.nmu.edu/sites/all/themes/omega_nmu/images/nmu_logo_white.png" alt="NMU Logo" title="Northern Michigan University" width="188" height"71" />`

As stated above, avoid putting images in tables whenever possible.

###Forms###
Forms should be laid out in a single column layout when the form label appearing on the line above the input field.

	**Name**
	[Input Field]

	**Address**
	[Input Field]

Forms laid out in this fashion are easier for a user to read and work best in mobile layouts.

When it makes sense to have some form elements appear in a multi-column layout, use the *form_l_float* class on the containing blocks to achieve this effect.  A div with the *form_clear* class should appear at the end of the floated elements.

	<p class="form_l_float">
		<strong>First Name:</strong><br />
		<input type="text" name="first_name" size="25" />
	</p>
	<p class="form_l_float">
		<strong>M.I.</strong><br />
		 <input type="text" name="middle_name" size="1"/>
	</p>
	<p class="form_l_float">
		<strong>Last Name:</strong><br />
		 <input type="text" name="last_name" size="34"/>
	</p>
	<div class="form_clear"></div>

Using this floating method will cause the elements to align in a column when space is available and in a row when space is not.

**Additional form classes**, the element they are typically applied to and their function:
-form\_indent: (block) 10px left margin
-form\_indent\_double: 30px (block) left margin
-form\_indent\_triple: 50px (block) left margin
-form\_border\_indent: (block) 10px left margin with left dotted border
-form\_border\_indent\_double: (block) 30px left margin with left dotted border
-form\_border\_indent\_triple: (block) 50px left margin with left dotted border
-form\_optional: (block) 10px left padding with left dashed border
-form\_l\_float: (block) left floated block with 10px left padding
-form\_clear: (block) clear all block floats
-form\_field\_spaced: (inline) 70px wide space {used for aligning labels and form fields on the same line -- see my adventure form}
-form\_note: (inline) 80% font size, italic
-form\_no\_indent: (block) 0px margin
-form\_error: (inline) red, italic, hidden by default {used for jQuery validation}
-form\_required\_item: (inline) red, italic {used for required asterisk}
-form\_hidden: (block) hidden by default {used for jQuery toggle}

[Block level elements][] included `<p>`, `<h1>`, `<ul>`, and `<div>`.  [Inline elements][] include `<span>`, `<strong>` and `<a>`.







[Block level elements](http://www.w3schools.com/html/html_blocks.asp)
[Inline elements](http://www.w3schools.com/html/html_blocks.asp)
