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


