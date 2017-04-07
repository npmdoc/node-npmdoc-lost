# api documentation for  [lost (v8.0.0)](http://lostgrid.org)  [![npm package](https://img.shields.io/npm/v/npmdoc-lost.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-lost) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-lost.svg)](https://travis-ci.org/npmdoc/node-npmdoc-lost)
#### LostGrid is a powerful grid system built in PostCSS that works with any preprocessor and even vanilla CSS.

[![NPM](https://nodei.co/npm/lost.png?downloads=true)](https://www.npmjs.com/package/lost)

[![apidoc](https://npmdoc.github.io/node-npmdoc-lost/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-lost_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-lost/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-lost/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-lost/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Cory Simmons & Peter Ramsing",
        "email": "hi@peterramsing.com",
        "url": "http://peter.coffee"
    },
    "bugs": {
        "url": "https://github.com/peterramsing/lost/issues"
    },
    "dependencies": {
        "object-assign": "^4.1.0",
        "postcss": "^5.2.8"
    },
    "description": "LostGrid is a powerful grid system built in PostCSS that works with any preprocessor and even vanilla CSS.",
    "devDependencies": {
        "chai": "^3.5",
        "eslint": "^3.12",
        "istanbul": "^0.4",
        "mocha": "^3.2"
    },
    "directories": {},
    "dist": {
        "shasum": "7ab03254f1106b6940abb2045c0e38f821a73475",
        "tarball": "https://registry.npmjs.org/lost/-/lost-8.0.0.tgz"
    },
    "gitHead": "396d6bddd38f5237159d37d834ad6df42d2f8cb7",
    "homepage": "http://lostgrid.org",
    "keywords": [
        "grid",
        "fraction",
        "ratio",
        "postcss",
        "postcss-plugin"
    ],
    "license": "MIT",
    "main": "lost.js",
    "maintainers": [
        {
            "name": "corysimmons",
            "email": "cory@launchboxhq.com"
        },
        {
            "name": "peterramsing",
            "email": "hi@peterramsing.com"
        }
    ],
    "name": "lost",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/peterramsing/lost.git"
    },
    "scripts": {
        "lint": "eslint lib/*.js lost.js",
        "test": "istanbul cover node_modules/mocha/bin/_mocha -- test/*.js"
    },
    "version": "8.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module lost](#apidoc.module.lost)
1.  [function <span class="apidocSignatureSpan">lost.</span>process (root, opts)](#apidoc.element.lost.process)
1.  object <span class="apidocSignatureSpan">lost.</span>_lg_logic

#### [module lost._lg_logic](#apidoc.module.lost._lg_logic)
1.  [function <span class="apidocSignatureSpan">lost._lg_logic.</span>calcValue (fraction, gutter, rounder, unit)](#apidoc.element.lost._lg_logic.calcValue)
1.  [function <span class="apidocSignatureSpan">lost._lg_logic.</span>validateUnit (value, validUnits)](#apidoc.element.lost._lg_logic.validateUnit)



# <a name="apidoc.module.lost"></a>[module lost](#apidoc.module.lost)

#### <a name="apidoc.element.lost.process"></a>[function <span class="apidocSignatureSpan">lost.</span>process (root, opts)](#apidoc.element.lost.process)
- description and source-code
```javascript
process = function (root, opts) {
  return postcss([creator(opts)]).process(root, opts);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.lost._lg_logic"></a>[module lost._lg_logic](#apidoc.module.lost._lg_logic)

#### <a name="apidoc.element.lost._lg_logic.calcValue"></a>[function <span class="apidocSignatureSpan">lost._lg_logic.</span>calcValue (fraction, gutter, rounder, unit)](#apidoc.element.lost._lg_logic.calcValue)
- description and source-code
```javascript
calcValue = function (fraction, gutter, rounder, unit) {
  var calcValue = '';
  var gutterLogic = '';

  if (!gutter) {
    gutter = '0';
  }

  if (gutter !== '0') {
    gutterLogic = ' - (${gutter} - ${gutter} * ${fraction})';
  }

  if (!unit) {
    unit = '%';
  }

  calcValue = 'calc(${rounder}${unit} * ${fraction}${gutterLogic})';
  return calcValue;
}
```
- example usage
```shell
...
      [0, 'auto']
    );
  }
}

decl.cloneBefore({
  prop: 'flex-basis',
  value: lgLogic.calcValue(lostColumn, lostColumnGutter, lostColumnRounder, unit)
});

if (gridDirection === 'rtl') {
  newBlock(
    decl,
    ':last-child',
    ['margin-left'],
...
```

#### <a name="apidoc.element.lost._lg_logic.validateUnit"></a>[function <span class="apidocSignatureSpan">lost._lg_logic.</span>validateUnit (value, validUnits)](#apidoc.element.lost._lg_logic.validateUnit)
- description and source-code
```javascript
validateUnit = function (value, validUnits) {
  var validation = false;

  if (validUnits.indexOf(value) !== -1) {
    validation = true;
  }
  return validation;
}
```
- example usage
```shell
...

    declaration.remove();
  }
});

decl.parent.nodes.forEach(declaration => {
  if (declaration.prop === 'lost-unit') {
    if (lgLogic.validateUnit(declaration.value, validUnits)) {
      unit = declaration.value;
    } else {
      decl.warn(result, '${declaration.value} is not a valid unit for lost-column');
    }
    declaration.remove();
  }
});
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
