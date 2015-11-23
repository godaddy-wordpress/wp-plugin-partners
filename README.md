# wp-test
WP Test


## Add using the Plugins API

If your plugin is already hosted for free on <a href="https://wordpress.org/plugins/">WordPress.org</a> you can simply use your plugin slug as the name of a new _empty_ object in the manifest and all of the data will be pulled directly from WordPress.org.

**EXAMPLE**

```json
{
  "akismet": {}
}
```

### Overriding certain fields

Occasionally, you may want to present data differently than it appears on WordPress.org. In this case you will need to indicate that you do want to use the Plugins API, and any additional fields you specify in the object will take precedence over Plugins API data.

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

If you are adding a plugin that is _not_ hosted on WordPress.org you will need to provide your own plugin data manually to the manifest.

Required fields:

* `name`
* `version`
* `author`
* `icon`
* `homepage`
* `short_description`

**EXAMPLE***

```json
"my-commercial-plugin": {
		"name": "My Commercial Plugin",
		"version": "1.0.0",
		"author": "<a href=\"https://mycompany.com\">Company Name</a>",
		"icon": "assets/images/my-commercial-plugin-icon.svg",
		"homepage": "https://mycompany.com/my-commercial-plugin",
		"short_description": "Just another WordPress plugin.",
		"requires": "4.1",
		"tested": "4.4",
		"last_updated": "2015-11-17 21:15:00"
}
```
