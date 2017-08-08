stylelint-find-rules
======================

[![Build Status](https://circleci.com/gh/alexilyaev/stylelint-find-rules.svg?&style=shield&circle-token=7fa54818dd54da41bad761661259992a74e50c7a)](https://circleci.com/gh/alexilyaev/stylelint-find-rules)
[![version](https://img.shields.io/npm/v/stylelint-find-rules.svg?style=flat-square)](http://npm.im/stylelint-find-rules)
[![MIT License](https://img.shields.io/npm/l/stylelint-find-rules.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![codebeat badge](https://codebeat.co/badges/10dc4306-cbef-4a6e-aa23-b197ee8ad3eb)](https://codebeat.co/projects/github-com-alexilyaev-stylelint-find-rules-master)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)


Find [Stylelint](https://github.com/stylelint/stylelint) rules that are not configured in your Stylelint config.

> Inspired by [eslint-find-rules](https://github.com/sarbbottam/eslint-find-rules)

Example Output
-----------------

![Example](example.png)

Installation
-------------

Install as a dev dependency of your project:

```
yarn add -D stylelint-find-rules
```

Or with `npm`

```
npm i -D stylelint-find-rules
```

Usage
------

This package requires `stylelint` to be installed in the project, as it will search for available
rules from that package.

### npm script

```
{
  ...
  "scripts": {
    "stylelint-find-unused-rules": "stylelint-find-rules"
  }
  ...
}
```

### Command line

```
./node_modules/.bin/stylelint-find-rules
```

Supported configs
------------------

Just like Stylelint, this package uses [cosmiconfig](https://github.com/davidtheclark/cosmiconfig)
to find your config data, so if Stylelint works for you, this should too.

### Custom config file

cosmiconfig supports a `--config` flag, so you can do:

```
./node_modules/.bin/stylelint-find-rules --config my-custom-config.js
```

### How does it handle `extends`?

The rules of `extends` are added to the list of configured rules, thus, if a rule is covered in an
extend config, it will not show up in the results.  
