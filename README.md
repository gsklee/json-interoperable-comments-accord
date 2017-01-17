JSON Interoperable Comments Accord
==================================

<ruby>**JSONICA**<rt>/dʒeɪˈsɒnɪkə/</rt></ruby> is a proposed convention for enabling a reasonable degree of comments interoperability between JSON and other data interchange formats or interfaces. It is not a “yet-another” new file format.

Introduction
------------

### What is JSON?

JSON is a “lightweight data interchange format”<sup>[[1]](http://www.json.org/)</sup> designed to “facilitate structured data interchange between all programming languages”<sup>[[2]](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf)</sup>. The format has enjoyed a great success in fulfilling that vision, receiving widespread adoption; however, such popularity has also led to an unwitting predicament.

In order to guarantee data interoperability - a fundamental requirement for a data interchange format - comments are not allowed in JSON <sup>[[3]](https://plus.google.com/+DouglasCrockfordEsq/posts/RK8qyGVaGSr)</sup>.




This document attempts to specify a standards-compliant JSON format that enables **comments interoperability** with other data serialization formats (eg. [TOML](https://github.com/toml-lang/toml), YAML, XML). The specification is intended to be a reference for module authors, and the format is intended to be generated and consumed solely by programs. While possible, it is not designed to be read or written by humans directly.

### What is JSONICA?

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

JSON is intended to be a [lightweight **data interchange** format](http://www.json.org/), and the absence of comments is a smart design decision to serve this purpose since comments are not part of the actual data payload, and rogue parsing directives hidden inside comments can pose harm to data interoperability.

JSON, however, is not a great format for **system configuration**. Configuration files are often regarded as part of the codebase - while data are not - and grow in complexity as the underlying system evolves over time. The lack of ability to add comments in configuration files can cause some real nuisance to the maintenance of real projects,

[literate programming](https://en.wikipedia.org/wiki/Literate_programming).





especially when the configuration is one that will . 




, due to the exact same reason that it lacks the ability to add comments.













