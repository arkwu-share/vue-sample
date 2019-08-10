# Host a vue app on github via gh-pages
## create vue project
```
vue create vue-sample

cd vue-sample
```

## the following works ONLY on cmd but NOT powershell due to { sign
```
echo module.exports = {>vue.config.js
echo   publicPath: process.env.NODE_ENV === 'production' ? '/vue-sample/' : '/'>>vue.config.js
echo }>>vue.config.js

npm i gh-pages
```

## prepare github repo
login to github and create a repo named vue-sample via https://github.com/new
get the git link https://github.com/arkwu-share/vue-sample.git

modify package.json file
added    "homepage": "https://arkwu-share.github.io/vue-sample",
added deploy under scripts    "deploy": "gh-pages -d dist",

## run the build
```
npm run lint
npm run build
```

## commit the code to master (optional if not publishing the code)
```
git add -A
git commit -m "added config.js file and added deploy script"
git remote add origin https://github.com/arkwu-share/vue-sample.git
git push -u origin master
```

## publish the code to gh-pages branches
```
npm run deploy
```