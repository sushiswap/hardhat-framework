# hardhat-framework
 
This package helps configuring a repo for hardhat development. This is very opinionated :)

### How to include this?
All the packages needed are included in this package, so all you need to add in your repo's `package.json` is:

```
"devDependencies": {
    "@sushiswap/hardhat-framework": "sushiswap/hardhat-framework"
}
```

### Setting up your .env
You can include your environment variables in a `.env` file in the root of your repo. Alternatively you can set an actual environment variable called `DOTENV_PATH` to point to a central `.env` file to be used. This way you can use the same environment settings accross multiple projects.

### Use default settings for configuration
Many settings are pre-defined in hardhat-framework. The following changes import all those settings as well as allow you to make any changes/additions to them in a central settings.js file.

To use the defaults defined in hardhat-framework, change or create the following files:

hardhat.config.js
```
const { get_hardhat_config, merge } = require("@sushiswap/hardhat-framework")
const { hardhat } = require("./settings")
module.exports = merge(get_hardhat_config(), hardhat)
```

.prettierrc.js
```
const { prettier_config, merge } = require("@sushiswap/hardhat-framework")
const { prettier } = require("./settings")
module.exports = merge(prettier_config, prettier)
```

.solcover.js
```

```