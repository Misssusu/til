#### 添加``viewport-fit=cover``meta标签，应对iPhoneX的刘海
#### viewport-fit的几个值
* auto 默认
* contain 页面内容显示在safe area内，同auto
* cover 页面内容充满屏幕
```html
<meta 
     name="viewport"
     content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, viewport-fit=cover"
>
```