<template>
    <div class="climb-wrapper">
        <section class="climb-text">
            <div class="block">
                <h1 >02.<span>CLIMB</span></h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa eum, est, doloremque animi tempora reprehenderit dignissimos amet laudantium officiis a.</p>
            </div>
        </section>
    </div>
    <div class="tab-wrapper" id="">
        <div class="tab-menu">
            <div class="menu-flex">
                <ul>
                    <li><a href="">MOUNTAIN 1</a></li>
                    <li><a href="">MOUNTAIN 2</a></li>
                </ul>
                <!-- <h4 class="">MOUNTAIN 1</h4>
                <h4 class="">MOUNTAIN 2</h4> -->
            </div>
        </div>
    </div>
    <div class="tab-content-bg">
        <section>
            <div>Mountain 1. Lorem ipsum dolor sit amet.</div>
            <div>Mountain 2. Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias, fugiat? </div>
        </section>
        <footer>

        </footer>
    </div>
</template>

<script>
import { ref } from 'vue'
   export default{
       setup(){
           const _activeTab = ref('mountain-one')
            const isActive = (tabitem) => {
                    _activeTab.value == tabitem
                }
            const setActive = (tabitem) => {
                    _activeTab.value == tabitem
                }

            return{isActive, setActive}
        }

   }

</script>

<style lang="scss" scoped>
.climb-wrapper{
    height: 200px;
     .climb-text{
          max-width: 780px;
          width: 90%;
          height: 100%;
          margin: auto;
        //   padding-top: 90px;
        .block{
            font-family: 'Oswald', sans-serif;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            h1{
                font-size: 135px;
                position: relative;
                color: #b0b4be;
                letter-spacing: -3.5px;
                height: 100%;
                span{
                    font-size: 32px;
                    vertical-align: middle;
                    display: inline-block;
                    position: relative;
                    left: 140px;
                    bottom: 210px;
                    color: #414f6b;
                    letter-spacing: -.7px;
                }
            }
            p{
                margin: 0 0 0 60px;
                width: 90%;
                font-family: 'Lato';
                font-weight: 300;
                font-size: 13px;
                line-height: 1.5em;
            }
        }
    }
}
.tab-wrapper{
        width: 100%;
        height: 50px;
        display: flex;
        justify-content: center;
        background: #414f6b;
        .tab-menu{
            max-width: 800px;
            width: 100%;
            margin: 0 5%;
            .menu-flex{
                    display: flex;
                    align-items: center;
                    height: 100%;
                    width: 220px;
                ul{
                    font-family: 'Oswald';
                    font-size: 20px;
                    font-weight: 700;
                    flex: 1;
                    width: 100%;
                    height: 100%;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    background: #414f6b;
                    color: #b0b4be;
                    text-decoration: underline;
                    cursor: pointer;
                    li{
                        list-style: none;
                        a{

                        }
                    }
                //     &:hover{
                //         background: #b0b4be;
                //         color: #414f6b;
                // }
            }
        }
    }
}
.tab-content-bg{
     background: url("../assets/bg2.png") top/cover no-repeat;
      min-height: 80vh;
      width: 100%;
      section{
          height:100%;
        }
    }
</style>