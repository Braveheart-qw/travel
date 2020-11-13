<template>
    <div id="heade">
        <div class="head_left">
            <span class="backIcon iconfont">&#xe70c;</span>
        </div>
        <div class="head_center">
            <input class="searchIcon iconfont" type="search" :placeholder='"\ue612"+"输入地名/城市/旅游景地"'>
        </div>
        <div class="head_right">
            <span class="jiantouIcon iconfont">城市&#xe64a;</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "heade"
    }
</script>

<style scoped lang="scss">
    #heade{
        display: flex;
        height: 1rem;
        background: #00bcd4;
        line-height: 1rem;

        .head_left{
            width: 1rem;
            text-align: center;
            .backIcon{
                font-size: 0.5rem;
            }
        }
        .head_center{
            flex: 1;
            margin: 0 0.2rem;
            input{
                width: 100%;
                border-radius: 0.1rem;
                height: 0.55rem;
                font-size: 0.2rem;
            }
        }
        .head_right{
            width: 1rem;
            text-align: center;
            padding-right: 0.1rem;
        }
    }
</style>