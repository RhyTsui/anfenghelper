# 01.客户端Webview交互测试
####  此用例基于JSBridge,测试请在安卓客户端内测试，[预览测试页](https://mikehumix.github.io/afaide/ "预览测试页") (index.html)

JSBridge是一个开源库，它是连接JAVA和JS的桥梁。
为什么要用JSBridge？ 
它提供了安全、方便的方式从js调用Java代码和调用js代码从Java。关于它的介绍看[这里](http://www.jianshu.com/p/9fd80b785de1 "这里")。

1. 方法:download,点击开始下载游戏，反馈暂停和开始状态。
2. 方法:open_game_detail,无需多言,熟人都能理解。
3. 方法:open_gift_detail,进入礼包详情
4. 方法:open_charge,点击进入充值页面，后面带参数可以直接选中金额。
5. 方法:open_game_special,点击进入任何游戏专辑
6. 方法:open_game_category,点击进入任何游戏分类
7. 方法:get_users_status,点击获得登录状态
8. 方法:get_version,获取版本信息
9. 方法:download_apk,下载普通APK
10. 方法:share,打开系统分享
11. 方法:firstpay,打开首充券
12. 方法:bind_phone,打开绑定手机页面
13. 方法:get_download_info,参数:down_url,获取游戏下载进度
14. 方法:install_game_package,获取游戏安装包名信息
15. 方法:install,参数:down_url,下载完成后的安装方法

#### 方法示例
    window.WebViewJavascriptBridge.callHandler('方法', {
            属性值
        },
        function(response) {
            方法执行成功后回调
        });

####调用游戏合辑
    window.WebViewJavascriptBridge.callHandler('open_game_special',
        {
            'id': 33,
            'name': 魔幻手游合辑
        },
        function(response) {}
    );

####调用游戏下载进度
    window.WebViewJavascriptBridge.callHandler('get_download_info',
        {
            'down_url': 01.apk
        },
        function(request) {}
    );


# 02.外部浏览器交互按钮实例
####  外部浏览器按钮实例，安卓系统浏览器测试，[预览测试页](https://mikehumix.github.io/afaide/index-web.html "预览测试页") (index-web.html)

1. 类型:type=1,属性url,外部浏览器打开H5页面
2. 类型:type=2,无属性,外部浏览器打开充值页面
3. 类型:type=3,属性url,外部浏览器打开签到页面
4. 类型:type=4,属性url,外部浏览器打开抽奖页面
5. 类型:type=5,无属性,外部浏览器打开首充券
6. 类型:type=6,无属性,外部浏览器打开任务中心
7. 类型:type=7,属性gameid,外部浏览器打开游戏详情
8. 类型:type=8,属性gameid,外部浏览器打开游戏预约详情
9. 类型:type=9,属性giftid,外部浏览器打开游戏礼包详情
10. 类型:type=10,属性collection_id和collection_name,外部浏览器打开游戏合辑

#### 示例
    anfan://af.app/game?type=7&gameid=800
