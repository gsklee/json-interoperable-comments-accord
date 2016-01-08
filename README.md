JSONIC: JSON with Interoperable Comments
========================================

This document attempts to specify a standards-compliant JSON format that enables **comments interoperability** with other data serialization formats (eg. [TOML](https://github.com/toml-lang/toml), YAML, XML). The specification is intended to be a reference for module authors, and the format is intended to be generated and consumed solely by programs. While possible, it is not designed to be read or written by humans directly.

Example
-------

```json
{
  "scripts": {
    "init": "./commands/init",
    "test": "./commands/test"
  },
  "dependencies": {
    "babel-core": "^5.8.30",
    "bound-native-methods": "^0.1.6",
    "isomorphic-fetch": "^2.2.0",
    "react": "^0.14.0",
    "react-dom": "^0.14.0",
    "classnames": "^2.2.0",
    "redux": "^3.0.4",
    "react-redux": "^4.0.0"
  },
  "devDependencies": {
    "webpack": "^1.12.2",
    "babel-runtime": "^5.8.29",
    "babel-loader": "^5.3.2",
    "express": "^4.13.3",
    "webpack-dev-middleware": "^1.2.0",
    "webpack-hot-middleware": "^2.4.1",
    "babel-plugin-react-transform": "^1.1.1",
    "react-transform-hmr": "^1.0.1",
    "react-transform-catch-errors": "^1.0.0",
    "redbox-react": "^1.1.1"
  },
  "#comments": {
    "scripts": {
      "init": ["", "$ npm run init"],
      "test": ["", "$ npm test"]
    },
    "dependencies": {
      "babel-core": ["ECMAScript 2015+"],
      "react": ["React"],
      "redux": ["Redux"]
    },
    "devDependencies": {
      "webpack": ["Webpack"],
      "express": ["Development Server"],
      "babel-plugin-react-transform": ["Hot Reload"]
    }
  }
}
```

Motivations
-----------

### Why? Douglas Crockford said no comments in JSON...

Indeed, [comments were barred from JSON](https://plus.google.com/+DouglasCrockfordEsq/posts/RK8qyGVaGSr) because Douglas didn't want to see IE conditional comments all over again. The problem is that JSON is being used nowadays in places beyond its original intentions.

JSON is intended to be a [lightweight **data interchange** format](http://www.json.org/), and the absence of comments is a smart design decision because comments are not part of the actual data payload, and rogue parsing directives hidden inside comments can harm data interoperability. JSON, however, is not a great format for **system configuration**, especially when the configuration will grow in complexity as the system evolves over time, due to the exact same reason that it lacks the ability to add comments.
