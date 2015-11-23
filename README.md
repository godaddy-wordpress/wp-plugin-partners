# WordPress Plugin Partners

## Add using the Plugins API

If your plugin is already hosted for free on <a href="https://wordpress.org/plugins/">WordPress.org</a> you can simply use your plugin slug as the name of a new _empty_ object in the manifest and all of the data will be pulled directly from WordPress.org.

**EXAMPLE**

```json
{
  "akismet": {}
}
```

### Overriding fields

Occasionally, you may want to present data differently than it appears on WordPress.org. In this case you will need to indicate that you _do_ want to use the Plugins API by declaring `"plugins_api": true`, and any additional fields you specify in the object will take precedence over Plugins API data.

**EXAMPLE**

```json
{
  "akismet": {
    "plugins_api": true,
    "name": "Akismet: Kissing SPAM Goodbye"
  }
}
```

## Add a commercial plugin

If you are adding a plugin that is _not_ hosted on WordPress.org you will need to provide _all_ of your plugin data in the manifest.

**Required fields:**

* `name` - The name of your plugin.
* `version` - The current version number of your plugin (we recommend [Semantic Versioning](http://semver.org/)).
* `author` - HTML anchor of the author name linking to the author homepage.
* `icon` - Relative path to your SVG icon under `assets/images/`.
* `homepage` - Homepage URL for your plugin (should be different from the author homepage).
* `short_description` - Describe your plugin in 140 characters or less.

**EXAMPLE**

```json
{
  "my-commercial-plugin": {
    "name": "My Commercial Plugin",
    "version": "1.0.0",
    "author": "<a href=\"https://mycompany.com\">Company Name</a>",
    "icon": "assets/images/my-commercial-plugin-icon.svg",
    "homepage": "https://mycompany.com/my-commercial-plugin",
    "short_description": "Just another WordPress plugin."
  }
}
```

## Other things you should know

* Changes will be visible to all users within 12 hours.
* Plugins are displayed to users in random order.
* Your icon asset should be in SVG format.
* All icons for commercial plugins are served through a CDN that is cached indefinitely. So if you decide to change your icon in the future you must push a **new asset** with a **new file name** and update the path in the manifest accordingly.
