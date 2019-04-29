# 移动端采坑

### IOS input导致页面上移
* 环境
  > IOS-微信浏览器
* 描述
  > input处于页面底部时，软键盘唤出后导致 整个页面上移，软键盘收起后页面未下滑，且软键盘阻挡了DOM节点的点击事件

* __解决方法__
  > input失去焦点后js调整滚动条位置
  ```
  document.querySelector('input').onblur = () => {
    document.body.scrollTop = document.body.scrollTop;
  }
  ```


