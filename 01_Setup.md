1. Android Studio
2. [jQuery mobile](https://www.w3schools.com/jquerymobile/jquerymobile_examples.asp)

# [Apache Cordova](https://cordova.apache.org/)

1. Follow the step [here](https://cordova.apache.org/docs/en/latest/guide/cli/) to create a Cordova Android application
2. Create a new emulator with Cordova or Android Studio
3. Go to the project folder and build the project with `cordova build android` and then run it with `cordova run android`
4. You should see a screen displaying "APACHE CORDOVA Device is ready"
5. To implement your own code, open the www folder under project repository and replace html, css and js files. Be aware to keep the `<head>` section of html file unless you know what you are doing

# Migrating a jQuery Mobile App to a Cordova Project
At this point we have our starter Cordova project set up and we can focus on migrating our jQuery Mobile application into it. The migration will consist of these steps:

1. Move the jQuery Mobile pages that today exist in their own separate html files over to the index.html file in the Cordova project.
2. Migrate the JavaScript files located under the project’s js directory over to the cordova-project/www/js directory.
3. Move the CSS files located the project’s CSS files from the CSS directory to the cordova-project/www/css directory.

https://dzone.com/articles/packaging-jquery-mobile
