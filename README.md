# slack-dark-theme

## Installing into slack

Find your Slack's application directory.

* Windows: `%homepath%\AppData\Local\slack\`
* Mac: `/Applications/Slack.app/Contents/`
* Linux: `/usr/lib/slack/` (Debian-based)

Navigate to the latest installed version and then open the following file in your favorite editor `resources/app.asar.unpacked/src/static/ssb-interop.js`

Add the following code at the end of the file
```js
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/ashutosh-shirole/slack-dark-theme/master/dark.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```

And thats it. Reload slack `Ctrl+R` and you should get a dark theme.

You will have to do this everytime you install/update your slack.
