# Android-WebView-Select
 An Android WebView-Friendly select pseudo-tag, based on the default HTML select tag that is interpreted based on OS which does NOT work on Android WebView, this is a workaround.

> IMPORTANT: Android-WebView-Select requires jQuery!

# CDN
Place this in your head tag.
```html
<script type="text/javascript" src="https://code.jquery.com/jquery-3.4.1.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/hostinfodev/Android-WebView-Select@main/dists/0.0.2/androidWebViewSelect.min.js"></script>
```

# Example
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title>Android-WebView-Friendly HTML Select Tag</title>
        <meta name="description" content="Android-WebView-Friendly HTML Select Tag">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <script type="text/javascript" src="https://code.jquery.com/jquery-3.4.1.js"></script>
        <script type="text/javascript" src="/src/androidWebViewSelect.js"></script>
    </head>
    <body>

        <h1>Android-WebView-Friendly HTML Select Tag</h1>

        <!--Our anchor element-->
        <div id="test" style="float: left;"></div>
        
        <!--Button to demonstrate how we can access the current selected value, externally-->
        <button id="btn" style="cursor:pointer;float: left;">Click Me</button>
        
        <!--INITIALIZE OUR SELECT-->
        <script>

            // Add our select options
            let options = [
                {name: "Option 1", value: "Value 1"},
                {name: "Option 2", value: "Value 2"},
                {name: "Option 3", value: "Value 3", disabled: true},
                {name: "Option 4", value: "Value 4"},
                {name: "Option 5", value: "Value 5"},
                {name: "Option 6", value: "Value 6"},
                {name: "Option 7", value: "Value 7"},
                {name: "Option 8", value: "Value 8"},
                {name: "Option 9", value: "Value 9"},
                {name: "Option 10", value: "Value 10"}
            ];

            // Add custom css classes
            let style = {wrapper: ['test_class'], options: ['test_class'], option: ['test_class']}

            // Define our onSelect callback
            let onSelect = (value) => {
                alert("Selected: " + value);
            }

            // Instantiate the class instance
            var ourSelectObject;
            ourSelectObject = new AndroidSelect(
                "#test",
                options,
                style = style,
                onSelect = onSelect
            )

            // Get the value from the class instance, externally
            $('#btn').on('click', () => {
                alert("Selected: " + ourSelectObject.value);
            })

        </script>
    </body>
</html>
```
### OnClick (button) Test
![](https://github.com/hostinfodev/Android-WebView-Select/blob/main/button_click_test.png?raw=true)

### OnSelect Test
![](https://github.com/hostinfodev/Android-WebView-Select/blob/main/onSelect_test.png?raw=true)