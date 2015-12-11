# node-logmatic

[Logmatic](http://logmatic.io/) TCP (over TLS) client

```
npm i -S node-logmatic
```

## Config

You need to pass down a config objects to node-logmatic for him to work.
It's defaults are as follow

```javascript
{
  token: undefined, // Required : your Logmatic token
  tcp: {
    host: 'api.logmatic.io',
    port: 10515
  },
  retryTimeout: 5000, // when failling to reconnect, this timeout if used for each retry
  defaultProps: {}, // add a default value to your log messages (like appname or hostname)
  logger: { //Define the logging functions used
    debug: _.noop,
    info: console.log.bind(console),
    warn: console.warn.bind(console),
    error: console.error.bind(console)
  }
}
```
Notes:
- There is only one mandatory field for you to define : **your logmatic token**
- The `tcp` object is passed to node [tls.connect](https://nodejs.org/api/tls.html#tls_tls_connect_options_callback).
