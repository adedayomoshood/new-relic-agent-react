# New Relic - React integration plugin

The package is based on [new-relic-react](https://github.com/reggi/new-relic-react) package by [reggi](https://github.com/reggi/) and later forked by [wanderio](https://github.com/wanderio/new-relic-react).
This variation includes a recent version of New Relic Browser plugin to inject [JavaScript snippet](https://docs.newrelic.com/docs/browser/new-relic-browser/page-load-timing/instrumentation-page-load-timing) to instrument your app's webpages.
The javascript provided in this library include all Pro and SPA features of [new relic's browser agent](https://docs.newrelic.com/docs/browser/new-relic-browser/getting-started/introduction-new-relic-browser).

It includes also [rollup.js](http://rollupjs.org/) to bundle source code as React component.

# Getting Started

`new-relic-react` can be installed as any other npm package.

# Installation

`npm install @shutterstock/new-relic-react --save`

# Application Structure
```
.
├── src                     # Source files
│   ├── .babelrc            # Babel transpiler configuration
│   ├── index.js            # New Relic - React component source code
├── rollup.config.js        # Rollup.js configuration file to bundle module
├── package.json            # Package information with list of dependencies
├── LICENSE.md
└── README.md
```

# Usage

Just import `NewRelic` into your component

Retrieve this information from your New Relic account
- licenseKey: New Relic account license key
- applicationID: Current New Relic application ID

```<NewRelic licenseKey="{licenseKey}" applicationID="{applicationID}" />```  
where licenseKey and applicationID are real IDs you retrieved

Following code is a super simple example of integration
```
import React from 'react'
import NewRelic from 'new-relic-react'

const Html = () => {
  return (
    <html>
      <head>
        <meta charSet="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <meta httpEquiv="x-ua-compatible" content="ie=edge" />
        <NewRelic licenseKey="xxxx" applicationID="yyyy" />
        <title>Web App</title>
      </head>
      <body>
        <div id="app">
          {children}
        </div>
      </body>
    </html>
  )
}

export default Html
```

# Changelog

1.1.0 - Added new js to support Pro + SPA features.  Updated agent to js-agent.newrelic.com/nr-1026.min.js. Made react a peer dependency.
1.0.5 - Updated newrelic agent to js-agent.newrelic.com/nr-1016.min.js  
1.0.4 - Updated newrelic agent to js-agent.newrelic.com/nr-974.min.js  
1.0.3 - Updated README.md and package.json to improve NPM description  
1.0.2 - Just fix some typos  
1.0.1 - Published scoped package on npm registry with additional rollup.js bundler and updated New Relic script

# License

Copyright (c) 2017 Shutterstock

MIT - http://opensource.org/licenses/mit-license.php

-----

based on https://github.com/wanderio/new-relic-react
