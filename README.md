# simpleMessenger

虎牙iframe通信信使(simple版)

* 使用示例

父页面：

```javascript

simpleMessenger.on('sayHello', function(data){
    alert('son said: ' + data)
})

```


子页面：

```javascript

if ('postMessage' in window) {
    window.parent.postMessage('{"code": "sayHello", "data": "Hi!"}', '*')
} 
else {
    try{
        window.navigator['onmessage']('{"code": "sayHello", "data": "Hi!"}') 
    } catch (e) {}
}

```
