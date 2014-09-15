goat
====

Serve static files for development, simple and unobstructive.

[![NPM][npm-badge]][npm-badge-link]

## Usage

```no-highlight
npm install -g goat
```

Then add it to your `package.json` as a script (you can also install without the `-g` for a single project):

```json
{
  "name": "my-project",
  "scripts": {
    "serve": "goat -e ./static/index.html ./dist"
  }
}
```

Which can now be executed in the terminal with `npm run serve`.

### Available Options

```no-highlight
Usage: goat [options]

Options:

  -h, --help                output usage information
  -V, --version             output the version number
  -e, --entry-file [file]   Usually an index.html, defaults to './index.html'
  -p, --port [port]         Port to run server on, defaults to 3000
  -d, --domain-host [host]  Host to serve static files at, defaults to 'localhost'
  -x, --debug               Enable development logging for debugging purposes
```

#### Multiple Static Directories

Any additional paths that you append to the end will be served as static directories.
When using `-e`, the parent directory is added as a static directory, so no need to add
it manually.

##### Custom Endpoints

For custom endpoints, use the `:` (colon) syntax. For example:

```no-highlight
goat -e ./static/index.html ./dist/scripts:/scripts
```

Would make everything in the scripts folder available at `localhost:3000/scripts`.

[npm-badge]: https://nodei.co/npm/goat.svg?stars=true
[npm-badge-link]: https://nodei.co/npm/goat/
