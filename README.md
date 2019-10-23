# tianmao1111auto.js
天猫自动脚步 领取猫币


天猫新出了活动,领金币,只因自己太懒,不想动,本来对auto.js也挺感兴趣的,就想练练手,昨天看了一下午官方API,晚上写出来了个 小作品吧相当于,很垃圾,很基本,适合新手看看.....大佬勿喷啊~~~~~,.........
测试手机  小米9  三星s7   没问题的下载auto.js  APP,(包里有)用法,看图片~~~下载地址:https://www.lanzous.com/i6x2asj

希望大佬们给点鼓励啊(疯狂暗示);;;;;





提示2340的,我重新改了一下
地址:https://www.lanzous.com/i6x32cb


/*************************************************************************/
再说一下用法啊,,,按图片装好之后,打开淘宝,点到活动页面不要动,直接点悬浮窗,开始运行脚本就行,提示2340或者1920的那是你当前手机的高,不用管的,会直接向下运行的.
打开活动页面不用动
打开活动页面不用动

打开活动页面不用动

直接运行脚本就行




/*********************************************************************************/
这次直接运行就行,不管在哪运行都可以了
,因为有人不会用,所以添加了自动打开淘宝
复制下面的代码   在auto.js里面  点蓝色的加号  再点  文件    随便起个名字  ,把代码 粘贴进去   运行就行
自己代码写的有点烂,希望有大佬来指点一下~~~~~~~~~


auto.waitFor();
var height = device.height;
var width = device.width;
toast("\n设备宽" + width + "\n" + "设备高" + height + "\n" + "手机型号" + device.model + "\n安卓版本" + device.release)
 
 
 
if (height == 1920) { //设置脚本坐标点击所适合的屏幕宽高。
    setScreenMetrics(1080, 1920);
    toast("设备高" + height);
    lingqu()
} else if (height == 2340) {
    setScreenMetrics(1080, 2340);
    toast("设备高" + height);
    lingqu()
}
else if (height == 2160) {
    setScreenMetrics(1080, 2160);
    toast("设备高" + height);
    lingqu();
}
function lingqu() {
    app.launchApp("手机淘宝");
    toast("打开淘宝")
    sleep(6000);
    click(600, 1235);//进入活动页
    sleep(6000);
 
    click(547, 1264);//点猫  领金币
    // //浏览15秒领金币
    sleep(1500);
    click(911, 1716);
 
    sleep(1500);
    if (text("签到").exists()) {
        text("签到").findOne().click();
        sleep(1600);
        toast("签到成功")
    }
    sleep(1500);
    while (text("去进店").exists()) {
        //要支持的动作
        toast("存在去进店");
        text("去进店").findOne().click();
        sleep(2500);
        swipe(width / 2, height - 600, width / 2, 0, 500);
        sleep(3500);
        swipe(width / 2, height - 600, width / 2, 0, 500);
        sleep(10000);
        swipe(width / 2, height - 600, width / 2, 0, 500);
        sleep(9000);
        back();
        sleep(1000);
    }
    while (text("去浏览").exists()) {
        //要支持的动作
        toast("存在去浏览");
        text("去浏览").findOne().click();
        sleep(1500);
        swipe(width / 2, height - 500, width / 2, 0, 500);
        sleep(2500);
        swipe(width / 2, height - 500, width / 2, 0, 500);
        sleep(10000);
        swipe(width / 2, height - 500, width / 2, 0, 500);
        sleep(8000);
        back();
        sleep(1600);
    }
 
    toast("结束");
}
