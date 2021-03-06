pushlytics
==========

Simple server to serve a pixel and record metrics in a LevelDB instance

## install

```sh
$ npm install -g pushlytics
```

## usage

```sh
usage: pushlytics [-hV] [-p port] [-r route] [-d dbpath] [-n dbprefix]
```

## example

```sh
$ pushlytics -p 8888 -r '/path/to/pixel.gif' -d /data/pixel -n analytics
```

All values in the query string are serialized into a `JSON` string and stored with its key being a call to `Date.now()`

```sh
$ curl localhost:8888/path/to/pixel.gif?user=1234&event=pageload
```

Use something like [lev](https://github.com/hij1nx/lev) or
[ldb](https://github.com/hij1nx/ldb) to read from the database on the
command line or read directly using
[level](https://github.com/level/level) and
[sublevel](https://github.com/dominictarr/level-sublevel).

## license

MIT
