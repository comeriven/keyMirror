pKeyMirror
=========

Create an object with values equal to its key names with/without prefix.

This is not my code, this is base on https://github.com/STRML/keyMirror.

Why?
----

From [this discussion](https://github.com/facebook/react/issues/1639#issuecomment-45188026):

when i use redux, i have to make many const as action

this tool can make diffrent const base on prefix and object key

the prefix value is related to router to make action uniq

Usage
-----

`npm install pkeymirror`

```javascript
var keyMirror = require('pkeymirror');
var LOGIN = keyMirror({INIT: null, SUBMIT: null},'LOGIN');
LOGIN.INIT === 'LOGIN_INIT'
```

The last line could not be performed if the values of the generated enum were
not equal to their keys.

Input:  `{key1: val1, key2: val2}`

Output: `{key1: key1, key2: key2}`

I sometimes use this with lodash - use the following upon your first use of lodash to mix it in:

```javascript
var _ = require('lodash');
_.mixin({keyMirror: require('keymirror')});
// Can now be used as _.keyMirror(object)
```


