![logo]()

# Slack-Custom-Dark-Theme

## Adding the Dark Theme

1) Make sure Slack is closed
2) Find Slack's `ssb-interop.js` file
    * For PC users, go to your version (your own username and current app version) of 
`C:\Users\username\AppData\Local\slack\app-3.1.0\resources\app.asar.unpacked\src\static`
Note that if your slack client updates, you'll need to do this process again for the updated version.
    * For Linux users, using the slack desktop (beta) navigate to `/lib/slack/resources/app.asar.unpacked/src/static`
    * Mac users, go to your version of 
`/Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static`
3) Open the file `ssb-interop.js` with your editor of choice.
4) Add all of the code below to the very end of file `ssb-interop.js` and save:
```
document.addEventListener('DOMContentLoaded', function () {
    $.ajax({
        url: 'https://raw.githubusercontent.com/jonnysandu/Slack-Custom-Dark-Theme/master/dark.css',
        success: function (css) {
            $("<style></style>").appendTo('head').html(css);
        }
    });
});
```
5) Open Slack

### Additional theme customization through Slack's theme editor

1) In Slack, click on Preferences
2) Click on sidebar
3) Scroll down click on custom theme
4) Paste these custom colors
`#23282d,#191e23,#0073AA,#FFFFFF,#111111,#EEEEEE,#46b450,#D54E21`


### What the Dark Theme + Custom Slack theme colors look like
![dark_theme]()
