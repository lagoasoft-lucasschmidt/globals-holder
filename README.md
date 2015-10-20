# Overview

Just a helper class that can hold options/configs and components.

# Install

``npm install globals-holder --save``

# API

- constructor([options])
    + accepts options
- option(key)
    + returns option set
- option(key, value)
    + sets value
- options()
    + returns object representing all options
- options(moreOptions)
    + sets moreOptions in current options
    + returns Globals
- component(key)
    + returns component
- component(key, value)
    + sets component
    + returns Globals
- fnOption(key)
    + returns option, throwing exception if its not a function
- bOption(key)
    + returns option, throwing exception if its not a boolean
- oOption(key)
    + returns option, throwing exception if its not an object
- sOption(key)
    + returns option, throwing exception if its not a string
- iOption(key, instance)
    + returns option, throwing exception if its not instanceof given instance
- config(key)
    + alias to option
- config(key, value)
    + alias to option
    + returns Globals

# Options
- failSilently *optional*
    + if this option is true, if you call APIs that throw exceptions, they wont be thrown

# Usage

```
myConfigs = {...}
globals = require('globals-holder')(myConfigs)
...
globals.component("service:user", new UserService())
...
```

```
module.exports = (globals)->
    dbUrl = globals.sOption("MONGO_URL")
    userService = globals.component("service:user")
    ...
```
