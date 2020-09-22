# gmde
### Online Markdown Editor
新一代的在线 Markdown 编辑器，轻巧、灵活、优雅。

# 简介
全名：GxzMarkdownEditor，非常自恋的采用了 Ganxiaozhe 的缩写，但这无关紧要，只需要他是个轻巧、灵活、优雅的编辑器足矣。
若要引用 GMDE 需先引用 v1.2.0 版本以上的 gQuery。
简单的引用：
```javascript
gxz.exEditor = new geditor('gmde-container',{pushHTML:1}).set({
   preview: '#ex-gmde'
});
```

# 关联插件
在引入以下插件后，GMDE 将自动调用他们：
- GazeImg 图片懒加载（链接待补充）
- [Highlight 代码高亮](https://highlightjs.org/download/)

# 自定义 GMDE
你可以随时通过 `.set(options)` 对 GMDE 进行自定义，包括实时预览、字符限制、自动保存以及文件上传功能。就像换装小游戏，想让他穿多少就穿多少 :3

## 实时预览
preview 对象接受一个 CSS3 选择器文本 以绑定预览。

## 字符限制
maxlength, minlength 对象分别接受一个 数值 以控制最小与最大字符数量限制。

## 自动保存
autoSave 对象接受一个 对象 以设置编辑器自动保存。
```
gxz.exEditor = new geditor('gmde-container',{pushHTML:1}).set({
    preview: '#ex-gmde',
    autoSave: {name: 'example',load: 1,time: 60}
});
```
`name:String` 设定保存数据的 **storage key**；`load:Number` 设定是否自动加载保存的内容，不为 1 时将不会自动加载；`time:Number` 设定自动保存的间隔时间（秒），默认为 30。

## 文件上传
upload 对象接受一个 对象 以控制文件上传模块，目前仅支持图片上传，且需部署后端以请求 token。
```
gxz.exEditor = new geditor('gmde-container',{pushHTML:1}).set({
    preview: '#ex-gmde',
    upload: {
       img: {
           allow: true,
           url: '/lib/sdk/ali-oss/get.php?action=',
           act: 'proj_imgUp',
           maxSize: 512*1024
       }
    }
});
```
