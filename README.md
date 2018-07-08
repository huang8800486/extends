* JQuery开发插件的两个方法
* 1.jQuery.extend(object);为扩展jQuery类本身.为类添加新的方法。 
* 2.jQuery.fn.extend(object);给jQuery对象添加方法。

# jQuery.extend(object) 为jQuery类添加类方法，可以理解为添加静态方法。
``` bash
!(function ($) {
    jQuery.extend({
        // 版本
        "version": "0",

        // 字母+数字，字母+特殊字符，数字+特殊字符
        "verifyPwd": function (str) {
            var patrn = /^(?![a-zA-z]+$)(?!\d+$)(?![!@#$%^&*.><]+$)[a-zA-Z\d!@#$%^&*.><]+$/;
            if (!patrn.exec(str)) return false
            return true;
        }
    });
})(window.jQuery);
// 调用
console.log($.version)
console.log($.verifyPwd("121213ijj"))
```
# jQuery.fn.extend(object);给jQuery对象添加方法。
# jQuery.fn = jQuery.prototype。等于prototype（原型）
``` bash
!(function ($) {
    jQuery.fn.extend({
        alertWhileClick: function() {
            $(this).click(function() {
                alert($(this).val());
            });
        }
    });
})(window.jQuery);

//$("#number")是jQuery的实例，调用这个扩展方法
$("#number").alertWhileClick();
```
