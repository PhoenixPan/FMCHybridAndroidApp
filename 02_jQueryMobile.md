# Preparation
1. Load jQuery mobile css and js and **jQuery js** files in `<head>`. We may need to move js files to the bottom of `<body>`
2. Load `<meta name="viewport" content="width=device-width, initial-scale=1">` in `<head>` to stablize the display size


### Prefetching pages
Use `data-prefetch="true"` to preload pages
`<a href="../pages-dialog/dialog-alt.html" data-prefetch="true">This link will prefetch the page</a>`
