![logo](https://github.com/jonnysandu/Slack-Custom-Dark-Theme/blob/master/slack-logo-bw.png)

Tired of that eye melting white background when using the Slack app? Cry no more child, cry no more.

## Adding the Dark Theme

1) Close the Slack Application
2) Find the file named `ssb-interop.js`
    * For PC, go to your version (your own username and current app version) of `C:\Users\juanito\AppData\Local\slack\app-3.1.0\resources\app.asar.unpacked\src\static`
    * For Linux, goto `/lib/slack/resources/app.asar.unpacked/src/static`
    * For Mac, go to `/Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static`
3) Open `ssb-interop.js` with your editor of choice
4) Add all of the code below to the very end of `ssb-interop.js`, make sure to save:
```
document.addEventListener('DOMContentLoaded', function () {
    $.ajax({
        url: 'https://raw.githubusercontent.com/jonnysandu/Slack-Custom-Dark-Theme/master/dark_theme.css',
        success: function (css) {
            $("<style></style>").appendTo('head').html(css);
        }
    });
});
```

   * If you want to use your own styles, adjust the line 
`url: 'https://raw.githubusercontent.com/jonnysandu/Slack-Custom-Dark-Theme/master/dark_theme.css'` to use your own css file. I recommend `https://gist.github.com/` as an easy quick way to set that up.

5) Open Slack, you should see the proposed changes.


_Tip: Open slack in developer mode on Mac so you can use developer tools like "inspect element"._

`export SLACK_DEVELOPER_MENU=true; open -a /Applications/Slack.app`


### Slacks own custom theme editor

To match the existing `dark_theme.css` styles provided, I personally use these custom colors. Feel free to change this to your own preferences. 

1) In Slack, click on Preferences
2) Click on sidebar
3) Scroll down click on custom theme
4) Paste these custom colors
`#23282d,#191e23,#0073AA,#FFFFFF,#111111,#EEEEEE,#46b450,#D54E21`


### Dark Theme + Slack theme customizations
![dark_theme](https://github.com/jonnysandu/Slack-Custom-Dark-Theme/blob/master/dark-theme-preview.png)

***Note that these changes will have to be reapplied every time Slack updates. If you're interested in a script I wrote to automatically apply changes on update, message me.**
