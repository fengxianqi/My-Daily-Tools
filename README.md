# My-Daily-Tools


~~~ bash

$(function(){


//递归调用，循环
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


~~~ bash
