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
4. Grid: http://demos.jquerymobile.com/1.4.5/grids/
5. Loader: http://demos.jquerymobile.com/1.4.5/loader/
6. Disabled Range slide: http://demos.jquerymobile.com/1.4.5/rangeslider/
7. Buttons in tool bar: http://demos.jquerymobile.com/1.4.5/toolbar/

# Page
One page is showed at a time. We can trigger events at different stages of page activity. 

```
// Flip to main page after a certain period
$("#page-splash").on("pageshow", function() {
    setTimeout(function () {
    $("body").pagecontainer("change", "#page-index", {
        transition: "flip"
    });
}, 2000);
});
```
