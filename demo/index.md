---
title: demo
layout: false
comment: false
date: 2016-09-19 23:35:26
---
<style>
    .divider{
        width: 100%;
        height: 3px;
        padding: 0 10%;
    }
</style>
<style type="text/css">
    .row{
        width: 300px;
        height: 100px;
        /*background-color: pink;*/
    }
    .alphaRadio{
        display: inline-block;
        height: 20px;
        line-height: 20px;
        text-align: left;
        cursor: pointer;
        margin-right: 10px;
    }
    .alphaRadio span,
    .alphaRadio i{
        display: inline-block;
        vertical-align: middle;
    }
    .alphaRadio i{
        width: 12px;
        height: 12px;
        border: 2px solid #333;
        border-radius: 50%;
        position: relative;
        top: 2px;
    }
    .alphaRadio span{
        margin-left: -3px;
        color: #333;
    }
    .alphaRadio [type="radio"]{
        display: none;
    }
    .alphaRadio.checked i:after{
        content: "";
        display: inline-block;
        width: 8px;
        height: 8px;
        border-radius: 50%;
        background-color: #333;
        position: absolute;
        top: 2px;
        left: 2px;
    }
</style>
<!-- 自定义单选控件 -->
<div class="row">
    <label class="alphaRadio checked" for="radio1" data-check="checked">
        <i></i>
        <input type="radio" name="gender" id="radio1" value="male">
        <span>male</span>
    </label>
    <label class="alphaRadio" for="radio2">
        <i></i>
        <input type="radio" name="gender" id="radio2" value="female">
        <span>female</span>
    </label>
</div>
<script src="/js/jquery.js"></script>
<script>
$(document).ready(function($){
    var alphaRadioElem = $('.alphaRadio');
    alphaRadioElem.each(function(index, elem){
        var _this = $(this);
        if (_this.attr('data-check') === 'checked') {
            _this.find('[type="radio"]').eq(0).prop('checked','checked');
        }
    });

    $('body').off('click', '.alphaRadio').on('click', '.alphaRadio', function(event){
        $(this).prop('checked', 'checked').addClass('checked').siblings('.alphaRadio').each(function(index, elem){
            $(this).prop('checked', '').removeClass('checked');
        });
    });
})
</script>
<div class="divider"></div>

