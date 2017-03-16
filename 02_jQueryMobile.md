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
Event order: http://www.gajotres.net/page-events-order-in-jquery-mobile/

## Use original functions from JavaScript
Use "bind" and write original functions in between:

```

$("#register-age").bind("change", function (event, ui) {
    var registerAgeIndex = document.querySelector("#register-age").selectedIndex; // selectedIndex does not work in jQ Mobile
    if (registerAgeIndex == 1) {
        document.querySelector("register-underage-hint").css("display", "block")
    }
});
```

## Submit form

## Open external links
```
<a target="_blank" data-rel="external" href="https://www.example.com">Link</a>
```


## Checkbox position adjustion
1.2em
```
.checkbox-control-div .ui-block-a input {
    height: 1.2em;
}
```

## Validation
```
// Registration form handler
$("#register-form").ready(function() {
    $("#register-form").validate({
        rules: {
            fname: {
                required: true
            },
            lname: {
                required: true
            },
            gender: {
                required: true
            },
            age: {
                required: true
            },
            under18checkbox: {
                // Conditional requirement, required only if one age has been selected
                required: function() {
                    return  document.querySelector("#register-age").selectedIndex == 1; 
                }
            },
            email: {
                required: true,
                email: true
            },
            postcode: {
                required: true,
                digits: true  // digits only
            },
            password: {
                required: true,
                minlength: 6
            },
            passwordconfirm: {
                required: true,
                minlength: 6,
                equalTo: "#register-password"
            },
            policy: {
                required: true
            }
        },
        messages: {
            fname: {
                required: "First name is required"
            },
            lname: {
                required: "Last name is required"
            },
            gender: {
                required: "The gender you identify as is required"
            },
            age: {
                required: "Your age is required"
            },
            under18checkbox: {
                required: "Your parent or guardian must accept the above Terms of Use, Guidlines, and Privacy Policy"
            },
            email: {
                required: "Email address is required",
                email: "Please enter a valid email address"
            },
            postcode: {
                required: "Your postcode is required",
                digits: "Postcode should contain only digits"
            },
            password: {
                required: "Password is required",
                minlength: "Your password should have at least 6 digits"
            },
            passwordconfirm: {
                required: "Password confirmation is required",
                minlength: "Your password should have at least 6 digits",
                equalTo: "Password does not match"
            },
            policy: {
                required: "You must accept the above Terms of Use, Guidlines, and Privacy Policy."
            }
        },
        errorPlacement: function(error, element) {
            error.insertAfter(element.parent("div"));
        },
        submitHandler: function () {
            $("body").pagecontainer('change', '#page-confirm', {
                reload: false
            });
            return false;
        }
    });
});
```
### Form submission
