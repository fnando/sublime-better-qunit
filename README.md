# Better QUnit

This is a custom QUnit package, that includes snippets, custom syntax highlighters and more!

**ATTENTION:** This plugin uses the new `.sublime-syntax` format, which is only available on [Dev Channel](http://www.sublimetext.com/3dev) Build 3084.

## Install

First of all, add this custom repository: <https://gist.github.com/fnando/56393d3900af55bf9e94>; just follow the instructions.

Then, install the `Better QUnit` package. Also, install the [ApplySyntax](https://github.com/facelessuser/ApplySyntax) package and use the following settings.

By the way, there is a [Better Rails](https://github.com/fnando/better-rails-for-sublime-text) package as well.

## ApplySyntax configuration

```json
{
  "new_file_syntax": "Better Ruby/Ruby",
  "reraise_exceptions": true,

  "syntaxes": [
    {
      "name": "Better QUnit/QUnit",
      "rules": [
        {"file_path": ".*_test\\.js$"}
      ]
    }
  ]
}
```

## Override Quote Style

By default, snippets use `'` as the preferred quote style. If you want to change it to `"`, just create the file `Packages/Users/QUnit-Quotes.tmPreferences` with the following content:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>name</key>
  <string>Quotes</string>
  <key>scope</key>
  <string>source.js</string>
  <key>settings</key>
  <dict>
    <key>shellVariables</key>
    <array>
      <dict>
        <key>name</key>
        <string>TM_QUOTE</string>
        <key>value</key>
        <string>"</string>
      </dict>
    </array>
  </dict>
  <key>uuid</key>
  <string>0FBD0784-F200-433C-AFFF-7F02BD6F7DB0</string>
</dict>
</plist>
```

## Override assert receiver

By default it's all assertion methods will be prefixed with `assert.`. You can disable this behavior by creating a `QUnit-Assert.tmPreferences` file like the following:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>name</key>
    <string>Quotes</string>
    <key>scope</key>
    <string>source.js.qunit</string>
    <key>settings</key>
    <dict>
        <key>shellVariables</key>
        <array>
            <dict>
                <key>name</key>
                <string>QUNIT_ASSERT_PREFIX</string>
                <key>value</key>
                <string></string>
            </dict>
        </array>
    </dict>
    <key>uuid</key>
    <string>0FBD0784-F200-433C-AFFF-7F02BD6F7DB0</string>
</dict>
</plist>
```

## Override QUnit receiver

Similarly, some things will use the `QUnit` receiver, like `QUnit.test`. You can disable this behavior by creating a `QUnit-Module.tmPreferences` file like the following:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>name</key>
    <string>Quotes</string>
    <key>scope</key>
    <string>source.js.qunit</string>
    <key>settings</key>
    <dict>
        <key>shellVariables</key>
        <array>
            <dict>
                <key>name</key>
                <string>QUNIT_PREFIX</string>
                <key>value</key>
                <string></string>
            </dict>
        </array>
    </dict>
    <key>uuid</key>
    <string>0FBD0784-F200-433C-AFFF-7F02BD6F7DB0</string>
</dict>
</plist>
```
