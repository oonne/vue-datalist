# vue-datalist
------------
A solution that mimics datalist on Safari/iOS

### Demo
[Demo](https://oonne.github.io/vue-datalist/)


### How to start
* install dependencies
> npm install

* run server
> npm run test

* browse 'localhost:3000'


### Description

``` javascript
import Datalist from './components/Datalist'

<Datalist
  :val="val"
  :list="list"
  :setVal="setValFun"
/>
```

### Props
* val: - string,

* list: - array,

* setVal: - function,

* maxRow: - int - default 5.


