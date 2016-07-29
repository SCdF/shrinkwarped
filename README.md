# shrinkwarped

Testing whether npm shrinkwrap actually ignores all dev dependencies.

This `package.json` contains no production dependencies and one development dependency.

So, if you run `npm install && npm shrinkwrap` should get an empty shrinkwrap file, with no packages recorded.

This currently doesn't work on:

```sh
$ node --version
v6.3.0
$ npm --version
3.10.5
```
