# js 实现一个简单的Popver效果

| 当鼠标滑过按钮时，显示Popver；当鼠标移出按钮时，隐藏Popver
| 当鼠标在Popver内时，显示Popver；当鼠标移出Popver时，隐藏Popver

### CSS只列出了大概，具体的样式还需要自己编写.

```html
<button id="btn">Popver</button>
<div class="my-popver" id="myPopver">
  <h1>这里是Popver的内容</h1>
</div>
```

```css
.my-popver {
  position: absolute;
  left: 250px;
  top: 60px;
  max-width: calc(100% - 250px);
  max-height: calc(100% - 60px);
  min-width: 30%;
  min-height: 200px;
  font-size: 14px;
  padding: 20px;
  background-color: #fff;
  border: 1px solid #ebeef5;
  border-radius: 4px;
  box-shadow: 0 2px 12px 0 rgba(0,0,0,.1);
  display: none;
}
```

```javascript
let popverTimeout = null;
let btn = document.getElementById('btn');
let myPopver = document.getElementById('myPopver');
btn.addEventListener('mouseover', function () {
  myPopver.style.display = 'block';
});
btn.addEventListener('mouseleave', function () {
  popverTimeout = setTimeout(function () {
    myPopver.style.display = 'none';
  }, 300);
});
myPopver.addEventListener('mouseover', function () {
  if (popverTimeout !== null) {
    clearTimeout(popverTimeout);
  }
});
myPopver.addEventListener('mouseleave', function () {
  popverTimeout = setTimeout(function () {
    myPopver.style.display = 'none';
  }, 300);
});
```
