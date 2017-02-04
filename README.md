# :star: Hack your :see_no_evil: vote out of :chart_with_upwards_trend: Polldaddy surveys - used by :moneybag: BBC, Microsoft, Forbes, Pfizer, IBM
[![JavaScript Style Guide](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/)
[![Build Status](https://travis-ci.org/hfreire/pollmommy.svg?branch=master)](https://travis-ci.org/hfreire/pollmommy)
[![codecov](https://codecov.io/gh/hfreire/pollmommy/branch/master/graph/badge.svg)](https://codecov.io/gh/hfreire/pollmommy)
[![Dependency Status](https://img.shields.io/david/hfreire/pollmommy.svg?style=flat)](https://david-dm.org/hfreire/pollmommy)
[![](https://img.shields.io/github/release/hfreire/pollmommy.svg)](https://github.com/hfreire/pollmommy/releases)
[![](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/npm/v/pollmommy.svg)](https://www.npmjs.com/package/pollmommy)
[![Downloads](https://img.shields.io/npm/dt/pollmommy.svg)](https://www.npmjs.com/package/pollmommy) 

Uses a headless browser to visit a poll website and inject JavaScript code to perform the desired poll voting. 

<img src="https://raw.githubusercontent.com/hfreire/pollmommy/master/share/github/voting-screencapture.gif" width="430">

### Dependencies
* Uses [Nightmare.js](http://www.nightmarejs.org/) :scream: to generate legit traffic on the poll website
* Supports [Bluebird](https://github.com/petkaantonov/bluebird) :bird: promises

### How to install (globally)
```
sudo npm install pollmommy -g
```

### How to fetch the required parameters
* URL - The poll's website URL, can be Polldaddy's website or the embedded poll website.
* Poll identifier - The Polldaddy's poll identifier, inspect the website HTML code and look for this pattern PDI_container<number> - <number> will be the id.
* Poll option identifier - The Polldaddy's poll option identifier, picke the desired option and inspect the website HTML code and look for this pattern PDI_answer<number> - <number> will be the id.

### How to use it in the terminal
```bash
pollmommy http://bbc.co.uk/should-trump-be-fired.html 324345 12939
```

### How to use it in your app
```javascript
const Pollmommy = require('pollmommy')
const pollmommy = new Pollmommy()

pollmommy.vote('http://bbc.co.uk/should-trump-be-fired.html', 324345, 12939)
  .then(() => console.log('Voted successfully!'))
  .catch((error) => console.error(error.message))
```
