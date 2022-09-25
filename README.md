# Babel.js Cheat Sheet


## Example package.json
```javascript
{
  "name": "test",
  "type": "module",
  "version": "1.0.0",
  "description": "test",
  "main": "src/index.js",
  "engines": {
    "node": ">=18.2.0",
    "npm": ">=8.9.0"
  },
  "scripts": {
    "build": "babel src -d build/src --ignore src/Docs.js --source-maps --copy-files",
    "unit-test": "npm run build && mocha 'build/src/test/unit/**/*.test.js' --recursive --timeout 0 --exit --reporter mochawesome --reporter-options reportDir=./website/report",
    "integration-test": "npm run build && mocha 'build/src/test/integration/**/*.test.js' --recursive --timeout 0 --exit --reporter mochawesome --reporter-options reportDir=./website/report",
    "start-dev": "npm run build && node build/index.js",
    "start": "npm run build && node build/index.js",
    "test": "npm run unit-test && npm run integration-test"
  },
  "mocha": {
    "file": [
      "./test/pretest.js"
    ]
  },
  "nodemonConfig": {
    "ignore": [
      "mochawesome-report/*"
    ]
  },
  "author": "CyberT33N",
  "license": "MIT",
  "devDependencies": {
    "@babel/cli": "^7.18.10",
    "@babel/core": "^7.19.1",
    "@babel/eslint-parser": "^7.19.1",
    "@babel/plugin-proposal-class-properties": "^7.18.6",
    "@babel/plugin-proposal-decorators": "^7.19.1",
    "@babel/plugin-proposal-export-namespace-from": "^7.18.9",
    "@babel/plugin-proposal-function-sent": "^7.18.6",
    "@babel/plugin-proposal-json-strings": "^7.18.6",
    "@babel/plugin-proposal-numeric-separator": "^7.18.6",
    "@babel/plugin-proposal-throw-expressions": "^7.18.6",
    "@babel/plugin-syntax-dynamic-import": "^7.8.3",
    "@babel/plugin-syntax-import-meta": "^7.10.4",
    "@babel/preset-env": "^7.19.1",
    "@babel/preset-stage-2": "^7.8.3",
    "chai": "^4.3.4",
    "chai-files": "^1.4.0",
    "eslint": "^8.24.0",
    "eslint-config-google": "^0.14.0",
    "firstline": "^2.0.2",
    "line-reader": "^0.4.0",
    "mocha": "^9.1.2",
    "mochawesome": "^7.1.3",
    "nodemon": "^2.0.13",
    "nyc": "^15.1.0"
  },
  "dependencies": {
    "axios": "^0.22.0",
    "axios-retry": "^3.2.0",
    "body-parser": "^1.19.0",
    "class-logger": "^1.3.0",
    "connect-timeout": "^1.9.0",
    "cookie-parser": "^1.4.5",
    "cors": "^2.8.5",
    "csurf": "^1.11.0",
    "csvtojson": "^2.0.10",
    "debug": "^4.3.2",
    "dotenv": "^10.0.0",
    "express": "^4.17.1",
    "express-async-errors": "^3.1.1",
    "express-rate-limit": "^5.4.0",
    "fancy-log": "^1.3.3",
    "fs-extra": "^10.0.0",
    "glob": "^7.2.0",
    "helmet": "^4.6.0",
    "lodash": "^4.17.21",
    "minimist": "^1.2.5",
    "mongodb": "^4.9.1",
    "mongoose": "^6.6.0",
    "morgan": "^1.10.0",
    "reflect-metadata": "^0.1.13"
  }
}
```

































<br><br>
__________________________________________________________
__________________________________________________________

<br><br>



## Babel CLI

<br><br>

### Ignore files for build
```
babel . --ignore node_modules,test --out-dir dist
```



<br><br>

### Copy all files
```
babel src --out-dir lib --copy-files
```
