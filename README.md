# jscalpel-orm
It is convenient for you to extract the required fields from one object to generate another object.

## Installation

#### Install using npm 
[![jscalpel-orm](https://nodei.co/npm/jscalpel-orm.png)](https://npmjs.org/package/jscalpel-orm)
``` 
npm install jscalpel-orm --save
yarn add jscalpel-orm --save
```

## Useage

#### Es6
```javascript
  import JscalpelORM from 'jscalpel-orm'
```
#### Include in html
```javascript
  <script charset="utf-8" src="https://unpkg.com/jscalpel-orm@latest/dist/index.js"></script>
  jscalpelORM.default
```
## APIS
| parameter	| type|	default value |	use|	isRequired	| required version   |
|----------|:-------------:|------:|------:|------:|------:|
| source |  object | empty object | source object | true | no |
| rules |    object   |   empty object | map rules |true |no |
| _extraInfo | object |   empty object | extra info |false |no |

## Demos
```javascript
// es6
import jscalpelORM from 'jscalpelORM';
const source = {
  data: {
    articles: [{
      imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
      title: ‘jscalpelORM'
    }],
  },
  msg: 'ok',
  code: 0,
}
const rules = {
  imgUrl: 'data.articles.0.imgUrl',
  msg: 'msg',
  articles: 'data.articles',
  title: 'data.articles.0.imgUrl',
};
const _extraInfo = {
  name: 'jscalpelORM',
};
const newTarget = jscalpelORM(source, rules, _extraInfo);
// output
{
 imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
 title: ‘jscalpelORM',
 articles: [{
   imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
   title: ‘jscalpelORM'
 }],
 msg: 'msg',
 name: 'jscalpelORM',
}
// es5
var source = {
  data: {
    articles: [{
      imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
      title: ‘jscalpelORM'
    }],
  },
  msg: 'ok',
  code: 0,
}
var rules = {
  imgUrl: 'data.articles.0.imgUrl',
  msg: 'msg',
  articles: 'data.articles',
  title: 'data.articles.0.imgUrl',
};
var _extraInfo = {
  name: 'jscalpelORM',
};
var newTarget = jscalpelORM(source, rules, _extraInfo);
// output
{
 imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
 title: ‘jscalpelORM',
 articles: [{
   imgUrl: 'https://avatars0.githubusercontent.com/u/6822604?s=460&v=4',
   title: ‘jscalpelORM'
 }],
 msg: 'msg',
 name: 'jscalpelORM',
}
```
