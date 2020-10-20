<template>
<div class="search-container">
    <form class="searchbox">
        <input type="search" placeholder="Nigga" name="search" class="searchbox-input" v-on:keyup.enter="buttonUp();" @focusin="handleSearch(true)" @focusout="handleSearch(false)" required>
        <span class="searchbox-icon"><i class="fa fa-search" aria-hidden="true"></i></span>
    </form>
</div>
</template>

<script>
import $ from 'jquery'

var searchBox, inputBox, submitIcon;

export default {
    mounted: function () {
        submitIcon = $('.searchbox-icon');
        inputBox = $('.searchbox-input');
        searchBox = $('.searchbox');

        submitIcon.mouseup(function () {
            return false;
        });
        searchBox.mouseup(function () {
            return false;
        });
        $(document).mouseup(function () {
            if (isOpen == true) {
                $('.searchbox-icon').css('display', 'block');
                submitIcon.click();
            }
        });
    },

    methods: {
        buttonUp: function () {
            var inputVal = $('.searchbox-input').val();
            inputVal = $.trim(inputVal).length;
            if (inputVal !== 0) {
                $('.searchbox-icon').css('display', 'none');
            } else {
                $('.searchbox-input').val('');
                $('.searchbox-icon').css('display', 'block');
            }
        },

        handleSearch: function (open) {
            if (open) {
                searchBox.addClass('searchbox-open');
                inputBox.focus();
            } else {
                searchBox.removeClass('searchbox-open');
                inputBox.focusout();
            }
        },
    },
}
</script>

<style>
.search-container {
    width: 25rem;
}

.searchbox {
    position: relative;
    min-width: 50px;
    width: 40%;
    height: 50px;
    float: right;
    overflow: hidden;

    -webkit-transition: width 0.3s;
    -moz-transition: width 0.3s;
    -ms-transition: width 0.3s;
    -o-transition: width 0.3s;
    transition: width 0.3s;
}

.searchbox-input {
    top: 0;
    right: 0;
    border: 0;
    outline: 0;
    background: #dcddd8;
    width: 100%;
    height: 50px;
    margin: 0;
    padding: 0px 55px 0px 20px;
    color: red;
}

.searchbox-input::-webkit-input-placeholder {
    color: #d74b4b;
}

.searchbox-input:-moz-placeholder {
    color: #d74b4b;
}

.searchbox-input::-moz-placeholder {
    color: #d74b4b;
}

.searchbox-input:-ms-input-placeholder {
    color: #d74b4b;
}

.searchbox-icon,
.searchbox-submit {
    width: 50px;
    height: 50px;
    display: block;
    position: absolute;
    top: 0;
    font-size: 22px;
    right: 0;
    padding: 0;
    margin: 0;
    border: 0;
    outline: 0;
    line-height: 50px;
    text-align: center;
    cursor: pointer;
    color: #FFFFFF;
    background: #ff0000;
}

.searchbox-open {
    width: 100%;
}
</style>
