# shrinkwarped

Testing whether npm shrinkwrap actually ignores all dev dependencies.

This `package.json` contains no production dependencies and one development dependency.

So, if you run `npm install && npm shrinkwrap` should get an empty shrinkwrap file, with no packages recorded.

What is happening with later version of node/npm, is that shrinkwrap is ignoring direct dev dependencies, but **is** including sub-dependencies of those dev dependecies.

This is currently broken on:

```sh
$ node --version
v6.3.0
$ npm --version
3.10.5
```

It looks like broke somewhere between:

```sh
$ node --version
v5.4.0
$ npm --version
3.8.5
```

which is broken, and:

```sh
$ node --version
v4.2.4
$ npm --version
2.14.12
```

which works as expected.
