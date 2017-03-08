# Preparation
1. Load jQuery mobile css and js and **jQuery js** files in `<head>` section. We may need to move js files to the bottom of `<body>` if they did not work correctly
2. Load `<meta name="viewport" content="width=device-width, initial-scale=1">` in `<head>` section to stablize the display size


### Prefetching pages
Use `data-prefetch="true"` to preload pages
`<a href="../pages-dialog/dialog-alt.html" data-prefetch="true">This link will prefetch the page</a>`

### UI
1. Inline button with icon `<a href="#" class="ui-btn ui-icon-delete ui-btn-icon-left ui-btn-inline">Anchor</a>`
2. Native button `<button data-role="none">Button</button>`

3. Login/submit `<form><input type="submit" value="Submit"></form>`
