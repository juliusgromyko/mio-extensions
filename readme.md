# MIO Extensions Formater Lib

Response formater midleware for express

Extract requested file type and parse data

# Quick Start

1) Add **extract()** as midleware

2) Add postfix **.:ext?** to the route

3) Use **render()** for response

4) Try to open your route at browser with adding .json, .xml or .html extension at the end or by changing requested mime type

# Sample

const extensions = require('mio-extensions');

... INIT express ...

app.use(extensions.extract);

... Update Routes ...

app.get('/error/:code?.:ext?')...

... Write Route function

extensions.render(req, res, {

  status: errorCode,

  template: './pathToYourTemplate/Vash.PuG',

  data: {

    code: errorCode,

    error: errorMessage,

    message: errorHint

  }

});

# Notes

This library just wrap up your logic, so it's agnostic to your template engine.

All options except **data** are optional
