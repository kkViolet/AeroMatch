# AeroMatch

移动端打包完要加上

```
document.addEventListener('DOMContentLoaded', function () {
    var canvas = document.getElementById('GameCanvas')
    if (canvas) {
      // 阻止触摸事件触发全屏
      canvas.addEventListener(
        'touchend',
        function (e) {
          e.preventDefault() // 阻止默认行为
        },
        { passive: false }
      )

      // 可选：阻止鼠标点击触发全屏（某些浏览器可能支持）
      canvas.addEventListener('click', function (e) {
        e.preventDefault()
      })
    }

    // 确保引擎不会自动全屏（针对 Cocos Creator 引擎）
    if (typeof cc !== 'undefined') {
      cc.view.enableAutoFullScreen(false)
    }
  })
})()
```
