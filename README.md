ssr-heroku
==================

Heroku
------

### Usage

```
$ heroku create
Creating qwertt... done, stack is cedar-14
http://qwertt.herokuapp.com/ | git@heroku.com:qwertt.git
```

Push the code to Heroku.

```
$ git push heroku master
…
-----> Compressing... done, 5.1MB
-----> Launching... done, v3
       http://qwertt.herokuapp.com/ deployed to Heroku

To git@heroku.com:qwertt.git
 * [new branch]      master -> master
```

Set a few configs:

```
$ heroku config:set METHOD=rc4 KEY=foobar
Setting config vars and restarting qwertt... done, v11
KEY:    foobar
METHOD: rc4
```

Install project dependencies with `npm install`:

```
$ npm install
…
```

Then run:

```
$ node local.js -s qwertt.herokuapp.com -l 1080 -m rc4 -k foobar -r 80
server listening at { address: '127.0.0.1', family: 'IPv4', port: 1080 }
```

Change proxy settings of your browser into:

```
SOCKS5 127.0.0.1:1080
```

### Troubleshooting

If there is something wrong, you can check the logs by:

```
$ heroku logs -t --app qwertt
```

Supported Ciphers
-----------------

- rc4
- rc4-md5
- table
- bf-cfb
- des-cfb
- rc2-cfb
- idea-cfb
- seed-cfb
- cast5-cfb
- aes-128-cfb
- aes-192-cfb
- aes-256-cfb
- camellia-256-cfb
- camellia-192-cfb
- camellia-128-cfb
