# Tampermonkey-Beginner油猴脚本入门
Start from removing SIGN IN when browsing articles on CSDN via Edge/Firefox

“Microsoft Edge 是油猴的强大插件。”（误）

1.下载与安装
打开油猴官网tampermonkey.net
根据使用的浏览器选择油猴下载版本，推荐安装Firefox或者Chrome，最好选择不含Beta的Stable版本
在extensions 中点击add to firefox

2.若上一步无法add，在火狐插件管理选择添加新脚本

3.创建新脚本
动机：因为访问csdn次数过多以后想要查看全文就需要登录才能看了，csdn中的内容都已经加载出来了,只不过是遮挡住了不让我看
点击油猴插件-->添加新脚本:
这里是一些常用的配置,以注释的形式呈现出来的,
    @name:脚本的名字,这里可以自己命名, 例如我们这个例子可以叫做"跳过csdn登录验证"
	@namespace:可以写自己的域名,当自己把脚本分享后,用户可以直接通过这儿找到你的具体功能实现
	@version:版本
    @description:功能描述,自己用就不用写
	@author:作者,可以写自己的网名
  
4.代码
  (function() {
    'use strict';

    // Your code here...
    就是这里,示例(csdn删除"查看更多"按钮,并显示全部页面内容):
    document.getElementById('article_content').removeAttribute('style');
    var del = document.getElementsByClassName('hide-article-box')[0].remove();
    del.parentNode.removeChild(del[0]);
    scrollTo(0,0);
})();

5.在CSDN刷新即可
点脚本->选择刚刚写的脚本->完成

感谢凉云https://www.cnblogs.com/liangyun/p/10168398.html
