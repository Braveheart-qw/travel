<template>
    <div id="index">
        <index_header></index_header>
        <Swiper v-if="swiperSlideItem">
            <div class="swiper-slide" v-for="i in swiperSlideItem" :key="i">
                <div class="menu">
                    <ul>
                        <li v-for="item1 in getSize(i)" :key="item1">
<!--                            每一个列表的样式-->
                            <div>
                                <img :src="getImg(i,item1)">
                                <br>
                                <span>{{getItem(i,item1)}}</span>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </Swiper>

    </div>
</template>

<script>
    import index_header from "../components/heade";
    import Swiper from '../components/swiper/swiper'
    export default {
        name: "index",
        data(){
          return {
              menuItem:[{name: '景点门票', path: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png'},
                        {name: '采石矶',   path: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b6e35d0668c434f6db6d7de07af3a307.png'},
                        {name: '本地玩乐', path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '自然风光', path:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png'},
                        {name: '踏青赏花', path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '香泉温泉', path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '翠林水城', path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '乔波冰雪', path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '西递村',  path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'},
                        {name: '全部玩乐',  path:'https://imgs.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'}],
              swiperSlideItem:null,
          }
        },
        mounted() {
            this.swiperSlideItem = Math.ceil(this.menuItem.length/8)
        },
        components: {
            index_header,
            Swiper,
        },
        computed:{
            getSize(){
                return (i)=> {
                    return (this.menuItem.length - 8*(i-1)) > 8 ? 8 : this.menuItem.length - 8*(i-1);
                }
            },
            getItem(){
                return (i, index)=> {
                    return this.menuItem[(index-1)+(i-1)*8].name
                }
            },
            getImg(){
                return (i, index)=> {
                    return this.menuItem[(index-1)+(i-1)*8].path
                }
            }
        }
    }

</script>

<style scoped lang="scss">
    #index{
        font-size: 0.32rem;
    }
    .menu{
        height: 100%;
        width: 100%;
        ul{
            display: flex;
            width: 100%;
            height: 100%;
            flex-wrap: wrap;
            li{
                flex: 1;
                width: 25%;

                /*问题：为什么flex-wrap不使用下面语句就不会生效*/
                min-width: 25%;
                max-width: 25%;
                div{
                    padding-top: 0.1rem;
                    img{
                        width: 1.1rem;
                    }
                    span{
                        font-size: 0.26rem;
                    }
                }
            }
        }
    }

</style>