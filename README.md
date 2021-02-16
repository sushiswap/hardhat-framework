# hardhat-framework
 
This package helps configuring a repo for hardhat development. This is very opinionated :)

### How to include this?
All the packages needed are included in this package, so all you need to add in your repo's `package.json` is:

```
    "scripts": {
        "test": "hardhat test",
        "format": "prettier --write contracts/**/*.sol *.js *.json test/**/*.js",
        "pretty-quick": "pretty-quick",
        "coverage": "hardhat coverage"
    },
    "devDependencies": {
        "@sushiswap/hardhat-framework": "sushiswap/hardhat-framework"
    }
```

### Setting up your .env
You can include your environment variables in a `.env` file in the root of your repo. Alternatively you can set an actual environment variable called `DOTENV_PATH` to point to a central `.env` file to be used. This way you can use the same environment settings accross multiple projects.

Some useful settings:
```
ALCHEMY_API_KEY=
COINMARKETCAP_API_KEY=
HARDHAT_NETWORK=hardhat
HARDHAT_MAX_MEMORY=4096
HARDHAT_SHOW_STACK_TRACES=true
HARDHAT_VERBOSE=true
```

### Use default settings for configuration
Many settings are pre-defined in hardhat-framework. The following changes import all those settings as well as allow you to make any changes/additions to them in a central settings.js file.

To use the defaults defined in hardhat-framework, change or create the following files:

**hardhat.config.js**
```
module.exports = require("@sushiswap/hardhat-framework").config.hardhat(require("./settings").hardhat)
```

**.prettierrc.js**
```
module.exports = require("@sushiswap/hardhat-framework").config.prettier(require("./settings").prettier)
```

**.solcover.js**
```
module.exports = require("@sushiswap/hardhat-framework").config.solcover(require("./settings").solcover)
```

And add a `settings.js` file:
```
module.exports = {
    hardhat: { },
    solcover: { },
    prettier: { }
}
```

TODO:

- Manage deployments
- Github hooks
- Getting husky to work properly (pre-commit in package.json)
- Integrate Certora
- Integrate Slither