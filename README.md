# PLUGINS.JS 插件

> WEB MOBILE plugins 

## Install

> copy pulgins.js 和 plugins.scss 到你的项目中,并在页面中引入以下代码

```
<link rel="stylesheet" href="css/plugins.css">
<script src="js/plugins.js"></script>

```

## Usage
> 以下插件使用时如果参数过多，建议通过 config 对象进行配置，而不是传入多个参数。


### Loading

```
    /**
     * 参数说明
     * @param text      显示的文本
     */
     
    $.showLoading('登录中...');
    
    setTimeout(function() {
        //关闭加载窗口
        $.hideLoading();
    }, 3000)

```


### alert

```
    /** 参数说明
     * @param text      自定义的消息内容    （必传参数）
     * @param title     标题
     * @param onOK      回调函数
     */
     
    $.alert("自定义的消息内容");
    
    $.alert("自定义的消息内容", "这是标题", function() {
        console.log("点击确认后的回调函数");
    });

```

### confirm

```
    /**
     * 参数说明
     * @param text      自定义的消息内容    （必传参数）
     * @param title     标题
     * @param onOK      确认回调函数
     * @param onCancel  取消回调函数
     */
     
    $.confirm("自定义的消息内容", function() {
        //点击确认后的回调函数
        console.log("点击确认后的回调函数");
        //如果参数过多，建议通过 object 方式传入
    }, function() {
        //点击取消后的回调函数
        console.log("点击取消后的回调函数");
    });
    
    $.confirm("自定义的消息内容", "这是标题", function() {
        //点击确认后的回调函数
        console.log("点击确认后的回调函数");
    }, function() {
        //点击取消后的回调函数
        console.log("点击取消后的回调函数");
    });

```


### prompt

```
    /**
     * 参数说明
     * @param text              自定义的消息内容    （必传参数）      
     * @param title             标题
     * @param onOK              确认回调函数 (value) 用户输入的值
     * @param onCancel          取消回调函数
     * @param defaultValue      默认值
     * @param inputType         输入框类型
     * @param placeholder       input占位符
     */
    
    $.prompt({
        title: '标题',
        text: '内容文案',
        defaultValue: '输入框默认值',
        empty: false, // 是否允许为空
        onOK: function (value) {
            //点击确认
        },
        onCancel: function () {
            //点击取消
        }
    });
```

### popup

```
    /**
     * 参数说明
     * @param text                  自定义的消息内容（支持HTML）    （必传参数）
     * @param title                 标题                         （必传参数）
     * @param img                   显示的图片                    （必传参数）
     * @param onOK                  确认回调函数 
     * @param onOkBtnText           确认按钮文本
     * @param onCancel              取消回调函数
     * @param onCancelBtnText       取消按钮文本
     */
     
     $.popup({
         title: '标题popup',
         text: '内容文案',
         img: './images/iphone_large.jpg',
         onOkBtnText:'了解更多',
         onOK: function () {
             //点击确认
             console.log("点击了解更多");
         },
         onCancelBtnText:'知道啦',
         onCancel: function () {
             //点击取消
             console.log("点击知道啦");
         }
     });
```

### modal  自定义对话框
```
    /**
     * 参数说明
     * @param params        详细参数见源码
     * @param onOpen
     */
    $.modal({
        title: "Hello",
        text: "我是自定义的modal",
        buttons: [
            { text: "支付宝", onClick: function(){ console.log(1)} },
            { text: "微信支付", onClick: function(){ console.log(2)} },
            { text: "取消", className: "default", onClick: function(){ console.log(3)} },
        ]
    });

```



## License

MIT © [Yang hc](https://github.com/hqwlkj)
