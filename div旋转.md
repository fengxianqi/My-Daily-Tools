
# div旋转 图片旋转
 - 注意：ie7/8不会转
 - 后面的classname直接用就行
 
 ~~~ bash
 @-webkit-keyframes rotate {
  0%,
  100% {
    -webkit-transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
  }
}
@-moz-keyframes rotate {
  0%,
  100% {
    -moz-transform: rotate(0deg);
  }
  100% {
    -moz-transform: rotate(360deg);
  }
}
@-o-keyframes rotate {
  0%,
  100% {
    -o-transform: rotate(0deg);
  }
  100% {
    -o-transform: rotate(360deg);
  }
}
@-ms-keyframes rotate {
  0%,
  100% {
    -ms-transform: rotate(0deg);
  }
  100% {
    -ms-transform: rotate(360deg);
  }
}
@keyframes rotate {
  0%,
  100% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.classname{//为了尽可能兼容各个浏览器
  -moz-animation: rotate 4s linear infinite;
  -webkit-animation: rotate 4s linear infinite;
  -o-animation: rotate 4s linear infinite;
  -ms-animation: rotate 4s linear infinite;
  animation: rotate 4s linear infinite;
}
 ~~~
