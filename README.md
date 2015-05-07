# express-logger-middleware
Express logger middleware - Ready to be used Out-Of-The-Box

## Basic Usage
First of all, call the module with `require`
```javascript
logger = require('express-logger-middleware')();
```
And then, use it as middleware
```javascript
app.use(logger.requestLogger); // log every request
app.use(logger.errorLogger); // log every error
```

---

## Advanced Usage
You can customize some the folliwing options
##### dataDir
Define the folder to write
##### logsDir
Define the logs folder, inside `dataDir`
##### generalLog
Define general log's filename.
##### accessLog
Define access log's filename.
##### errorLog
Define error log's filename.

#### Putting all together
```javascript
logger = require('express-logger-middleware')({
    dataDir: process.env.OPENSHIFT_DATA_DIR
  , logsDir: 'logs'
  , generalLog: 'info.log'
  , accessLog: 'request.log'
  , errorLog: 'error.log'
});
```
And then, use it as middleware.
```javascript
app.use(logger.requestLogger); // log every request
app.use(logger.errorLogger); // log every error
```




