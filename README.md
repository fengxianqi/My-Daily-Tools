# My-Daily-Tools




# 递归调用，循环
~~~ bash
$(function(){
var $btns = $('#btn-area').find('.btn');
    var timer = null;

     function topAnDown() {
        var UP = '-=10px',
            DOWN = '+=10px';
        $btns.animate({
            'top': UP
        }, 600, 'linear').animate({
            'top': DOWN
        }, 600, 'linear');
       timer = setTimeout(topAnDown,0);
    }

    topAnDown();
})
~~~ 



# 网易分享必填 
~~~ bash
$(function(){
    //nie.config.copyRight.setGray();
    var share = null;
    var shareUrl = $("#share_url").html();
    var sharePic = $("#share_pic").attr("data-src");
    var shareTxt = $("#share_desc").html();
    var shareTitle = $("#share_title").html();
    nie.define(function(){
        var share = nie.require("nie.util.shareV5");
        share({
            fat:"#NIE-share",
            type:1,
            defShow:[23,22,2,1,4,3],
            title:shareTitle,
            //url:shareUrl,
            img:sharePic,
            content:shareTxt,
            product:"产品号"
        });
    });
$("a").focus(function(){this.blur();});
});
~~~


# 网易视频调用
+ js部分
~~~ bash
$(function(){
    var video=null;
    $(".btn-movie").click(function() {
        $(".hide-box").toggle();
        $(".show-box").toggle(200);
        nie.define(function(){
            var videoModule = nie.require("nie.util.videoV2");
            video = videoModule({
            fat: "#videoShow", //放视频的容器
            width: "600", //视频宽度
            height: "400", //视频高度
            //wmode:"direct",//flash wmode值,默认direct
            movieUrl: "http://v.tx3.netease.com/2016/1107/9cd371bb8609c1c34ecc59a801bbde69qt.mp4", //标清视频地址
            HDmovieUrl: "", //高清视频地址
            SHDmovieUrl: "", //超清视频地址
            vtype: "", //默认选用哪种清晰度，分别有d,hd,shd，默认不填则会采用校验网速然后自动匹配
            autoPlay:true
            //是否自动播放，默认false
            //startImg:null,//开始图片地址，默认false
            //loopTimes:0,//循环播放次数，默认0
            //maskImg:null,//整个flash顶部遮罩图片地址，默认null
            //bufferTime:5//缓冲时间（秒）,默认5
        });
        });

    });

    $(".close").click(function(){
       $(".hide-box").toggle();
       $(".show-box").toggle(200);
       $("#videoShow").html("");

   });
~~~

+ html
~~~ bash
<!--视频弹层-->
<div class="hide-box"></div>
<div class="show-box">
 <div class="close"></div>
 <div class="videoBox" id="videoShow">
 </div>
</div>
~~~

+ css
~~~ bash
.hide-box{
      position: fixed;
      top:0;
      left:0;
      width: 100%;
      height: 100%;
      display: none; 
      background: black;
      filter:alpha(opacity=70);  
      -moz-opacity:0.7;  
      -khtml-opacity: 0.7;  
      opacity: 0.7;   
      z-index: 9999;
  }

  .show-box{
    display: none;
    width: 648px;
    height: 400px;
    position: fixed;
    top:50%;
    left: 50%;
    margin-left: -300px;
    margin-top: -200px;
    z-index: 100000;
    
}
.videoBox{
    float: left;
    width: 600px;
    height: 400px;
    display: block;
} 
.close{
    right: 0;
    height: 48px;
    width: 48px;
    position: absolute;
    top: 0;
    cursor:pointer;
    background: url("../images/close.png") no-repeat;
}
.close:hover{
    -webkit-transition: all .5s;
    -o-transition: all .5s;
    -moz-transition: all .5s;
    transition: all .5s; 

    -moz-transform: rotate(90deg);
    -o-transform: rotate(90deg);
    -webkit-transform: rotate(90deg);
    transform: rotate(90deg);
}
~~~




