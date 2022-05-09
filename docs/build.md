# Building for offline use on OSX / Mac using NodeJS 18

## Building the offline branch 

1. npm run setup
1. npm run build

### What's different

* A few package.json convenience scripts (clean, setup)
* All imgur images have been moved into the repo so it can be used offline
  * README.md updated during prebuild with the correct links for these

## Building upsteam (gcoulby source / master) on OSX / Mac using NodeJS 18

These are notes on getting the original author's verion built on OSX using NodeJS 18.

1. Remove `packaqe-lock.json` and `yarn.lock`
1. Remove `babel-loader`, `webpack`, `webpack-cli`, and `webpack-dev-server` from package.json
1. Update deps with `npm update --legacy-peer-deps`
1. Build with `./node_modules/react-scripts/bin/react-scripts.js build`

### Notes

* Be sure to use the react-scripts version in node-modules (not your global if you have one)

# Other Notes

## Setup your own Google Drive integration

Setup your google app with an oauth client ID and API key:

![image](https://user-images.githubusercontent.com/7715262/167339610-780ba3e2-4ccf-4c90-900b-fcffa281df1b.png)

On the `OAuth consent screen` choose the `See, edit, create, and delete only the specific Google Drive files you use with this app` scope (make sure you've enabled Google Drive API prior to this.

Before building and deploying the app, make sure you have a `.env` file in the root with the API key and the Client ID (you don't need to the Client Secret):

```
REACT_APP_GOOGLE_DRIVE_API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
REACT_APP_GOOGLE_DRIVE_CLIENT_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.apps.googleusercontent.com
```



