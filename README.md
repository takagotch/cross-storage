### cross-storage
---
https://github.com/zendesk/cross-storage

```js
CrossStorageHub.init([
  {origin: /\.example.com$/, allow: ['get']},
  {origin: /:\/\/(www\.)?example.com$/, allow: ['get', 'set', 'del']}
]);

var storage = new CrossStorageClient('https://store.example.com/hub.html');
storage.onConnect().then(function(){
  return storage.set('newKey', 'foobar');
}).then(function(){
  return storage.get('existingKey', 'newKey');
}).then(function(res){
  console.log(res.length);
}).catch(function(err){
});

var CrossStorageClient = require('cross-storage').CrossStorageClient;
var CrossStorageHub = require('cross-storage').CrossStorageHub;

CrossStorageHub.init([
  {origin: /localhost:3000$/, allow: ['get', 'set', 'del', 'getkeys', 'clear']}
]);

var storage = new CrossStorageClient('http://locahost:3000/hub.html');
var storage = new CrossStorageClient('http://localhost:3000/hub.html', {
  timeout: 5000,
  frameId: 'storageFrame'
});

storage.onConnet().then(function(){
});

storage.onConnect().then(function(){
  return storage.get('key1');
}).then(function(res){
  return storage.get('key1', 'key2', 'key3');
}).then(function(res){
});

storage.onConect().then(function(){
  return storage.del('key1', 'key2');
});

storage.onConnect().then(function(){
  return storage.getKeys();
}).then(function(keys){
});

storage.onConnect().then(function(){
  return storage.clear();
});

storage.onConnect().then(function(){
  return storage.set('key1', 'key2');
}).catch(function(err){
}).then(function(){
  storage.close();
});

storage.onConnect().then(function(){
  return storage.get('key1');
}).then(function(res){
})['catch'](function(err){
});
```

```
bower install cross-storage
npm install cross-storage
```

```
{
  'Access-Control-Allow-Origin': '*',
  'Access-Control-Allow-Methods': 'GET,PUT,POST,DELETE',
  'Access-Control-Allow-Headers': 'X-Requested-With',
  'Content-Security-Policy': "default-src 'unsafe-inline' *",
  'X-Content-Security-Policy': "default-src 'unsafe-inline' *",
  'X-Webkit-CSP': "default-src 'unsafe-inline' *",
}
```

