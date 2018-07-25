---
categories: [js]
---
##### localstorage 发生改变时 `其他页面` 会触发 `storage` 事件

当前页面
```
let a = 0
localstorage.setItem('x', a++)
```
其他页面
```
window.addEventListener('storage', data=>{
  // data.oldValue, data.newValue 分别表示改变前改变后的值，可根据实际情况使用
  if (data.key === 'a') {
    // do something
  }
})
```