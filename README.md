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

### IOS new Date() 方法不兼容
* 环境
  > IOS
* 描述
  > new Date() 传入 '2019-5-20' ,IOS无法正常解析

* __解决方法__
  > 将传入参数'2019-5-20'进行正则替换成'2019/5/20'
  ```
  let time = new Date('2019-5-20'.replace(/-/g, '/'))
  ```
