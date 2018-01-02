# 支付宝小程序开发遇见的问题汇总
1、swiper组件：如果data里有值，可以正常显示，但是如果开始没有值，是从后台拿的数据setData的，则没法正常显示，需要操作一下才会显示(如点一下图片、图片自动播放、10ms左右后再次调用setData等)。 
解决：直接在swiper和swiper-item中设定高度<swiper style="height:200px;"><swiper-item style="height:200px;"> 
2、swiper设置current值：直接使用按钮setData的话，只能有一次又效果或者基本没用，原因应该是swiper轮播的时候current是不变的。 
解决：swiper的onChange绑定函数，轮播的时候同步改变current的值。 
3、hidden属性：很多组件的hidden属性无效，包含但不限于text、button等等，没测试太多。解决：在外面套一层view，hidden直接放在view里。 
4、js的startsWith函数：开发者工具可以正常使用，真机预览和体验版这个函数是用不了的。。。ps：今天刚入坑，把一个简单的微信小程序改成了支付宝小程序提交审核了，目前就发现这些感觉挺坑的问题。
5、支付宝小程序不支持富文本解析
解决：将微信的wxparse控件拿过来进行修改可使用，但仅限于ide版本0.15.9及其以下版本，0.15.10版本不可用。
