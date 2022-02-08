<template>
    <div class="hero-banner" id="hero">
        <div class="hero-text"></div>
    </div>

    <div id="history">
        <section class="history-text">
            <div class="block">
                <h1 >01.<span>HISTORY</span></h1>
            </div>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin in ante viverra, rutrum erat rutrum, consectetur mi. Proin at maximus est. Nullam purus ex, iaculis sed erat sed, blandit tincidunt quam. Cras scelerisque id quam sed dignissim Pellentesque urna nunc, gravida quis hendrerit ac, tristique ut quam. Vivamus suscipit dignissim tortor nec congue.</p>
        </section>
        <div class="carousel">
            <Carousel />
        </div>
    </div>
      <div class="climb-wrapper" id="team">
        <section class="climb-text">
            <div class="block">
                <h1 >02.<span>CLIMB</span></h1>
                <p>Cras scelerisque id quam sed dignissim Pellentesque urna nunc, gravida quis hendrerit ac, tristique ut quam. Vivamus suscipit dignissim tortor nec congue.</p>
            </div>
        </section>
    </div>
    <div v-if="mobile" class="accordion-container">
        <accordion>
            <template v-slot:title>
                <span class="">MOUNTAIN 1</span>
            </template>
            <template v-slot:content>
                <div>
                    <div>
                    <h3>
                        SCHEDULE
                    </h3><br>
                        <p> 25 Nov 2016</p>
                        <p> Vestibulum viverra</p>
                        <p> 28 Nov 2016</p>
                        <p> Vestibulum viverra</p><br>
                        <p> 18 Dec 2016</p>
                        <p> Vestibulum viverra</p><br>
                        <p> 7 Jan 2017</p>
                        <p> Vestibulum viverra</p>
                    </div>
                </div>
            </template>
        </accordion>
        <accordion>
            <template v-slot:title>
                <span class="">MOUNTAIN 2</span>
            </template>
            <template v-slot:content>
            <div>
                    <div>
                    <h3>
                        SCHEDULE
                    </h3><br>
                        <p> 17 Nov 2016</p>
                        <p> Vestibulum viverra</p>
                        <p> 13 Nov 2016</p>
                        <p> Vestibulum viverra</p><br>
                        <p> 28 Dec 2016</p>
                        <p> Vestibulum viverra</p><br>
                        <p> 9 Feb 2017</p>
                        <p> Vestibulum viverra</p>
                    </div>
                </div>
            </template>
        </accordion>
    </div>
    <div v-else>
    <div class="tab-wrapper">
        <div class="tab-menu">
            <div class="menu-flex">
                <ul>
                    <li><a @click.prevent="setActive('mountain1')" href="#mountain1" :class="{active: isActive('mountain1')}">MOUNTAIN 1</a></li>
                    <li><a @click.prevent="setActive('mountain2')" href="#mountain2" :class="{active: isActive('mountain2')}">MOUNTAIN 2</a></li>
                </ul>
            </div>
        </div>
    </div>
    <div class="tab-content-bg">
        <section>
            <div class="container">
                <div class="hide" :class="{ 'active show' : isActive('mountain1')}" id="mountain1">
                    <h4>
                        SCHEDULE
                    </h4>
                    <div class="flex">
                        <p> 25 Nov 2016</p>
                        <p> Vestibulum viverra</p>
                    </div>
                    <div class="flex">
                        <p> 28 Nov 2016</p>
                        <p> Vestibulum viverra</p>
                    </div><br>
                    <div class="flex">
                        <p> 18 Dec 2016</p>
                        <p> Vestibulum viverra</p>
                    </div><br>
                    <div class="flex">
                        <p> 7 Jan 2017</p>
                        <p> Vestibulum viverra</p>
                    </div>
                </div>
                <div class="hide" :class="{ 'active show': isActive('mountain2')}" id="mountain2">
                      <h4>
                        SCHEDULE
                    </h4>
                    <div class="flex">
                        <p> 17 Nov 2016</p>
                        <p> Vestibulum viverra</p>
                    </div><br>
                    <div class="flex">
                        <p> 13 Dec 2016</p>
                        <p> Vestibulum viverra</p>
                    </div>
                    <div class="flex">
                        <p> 28 Dec 2016</p>
                        <p> Vestibulum viverra</p>
                    </div><br>
                    <div class="flex">
                        <p> 9 Feb 2017</p>
                        <p> Vestibulum viverra</p>
                    </div>
                </div>
            </div>
        </section>
    </div>
    </div>
</template>
<script>
import Carousel from "./Carousel";
import Accordion from "./Accordion";
// import Team from "./Team";
import {ref, onMounted} from 'vue';
export default{
    components: {Carousel, Accordion},
    setup(){
          const _activeTab = ref('mountain1')
          const windowWidth = ref(null)
          const mobile = ref(false)
            const isActive = (tabitem) => {
                   return _activeTab.value === tabitem
                }
            const setActive = (tabitem) => {
                    _activeTab.value = tabitem
                    // console.log( _activeTab.value)
                }
                 onMounted(() => { 
                window.addEventListener('load', screenWidth)
                window.addEventListener('resize', screenWidth)
            })
            const screenWidth = () => {
                windowWidth.value = window.innerWidth;
                if(windowWidth.value <= 425){
                    // console.log('hi')
                    mobile.value = true
                }else{
                    mobile.value = false
                }
              
            }

         return{isActive, setActive, mobile}
    }
}

</script>

<style lang="scss" scoped>
    .hero-banner{
      background: url("../assets/hero-banner.png") top/cover no-repeat, url("../assets/hero-text.png") top/cover no-repeat;
      min-height: 50vw;
      width: 100%;
    .hero-text{
      background: url("../assets/hero-text.png") top/cover no-repeat;
      min-height: 50vw;
      width: 100%;
    }
    }
    #history{
        background: url("../assets/peak.png") top/cover no-repeat;
        min-height: 120vh;
        background-color: #414f6b;
        background-blend-mode: hard-light;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
      .history-text{
          max-width: 900px;
          width: 100%;
          height: 100vh;
          margin: 0 auto;
          padding-top: 90px;
        //   margin-left: 280px;
        //   margin-right: 320px;
        position: relative;
        left: -6.5%;
        padding-left: 5%;
          .block{
            font-family: 'Oswald', sans-serif;
            height: 165px;
            h1{
                font-size: 135px;
                position: relative;
                color: #6d7d97;
                letter-spacing: -3.5px;
                span{
                    font-size: 32px;
                    vertical-align: middle;
                    display: inline-block;
                    position: relative;
                    left: -25px;
                    bottom: 7px;
                    color: #414f6b;
                    letter-spacing: -.7px;
                }
            }
        }
        p{
            padding-left: 73px;
            width: 100%;
            font-family: 'Lato';
            font-weight: 300;
            font-size: 13px;
            line-height: 1.5em;
        }
        }
        .carousel{
            height: auto;
            width: 100%;
            background-color: #3b475ed4;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px 5%;
            margin: auto;
    }
    }
    .climb-wrapper{
    height: 200px;
    // min-height: 200px;
     .climb-text{
          max-width: 900px;
          width: 90%;
          height: 100%;
          margin: auto;
          padding-left: 10px;
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
                    left: 143px;
                    bottom: 205px;
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
        position:relative;
        .tab-menu{
            max-width: 900px;
            width: 100%;
            margin: 0 5%;
            margin-left: 30px;
            // position: absolute;
            .menu-flex{
                    display: flex;
                    align-items: center;
                    height: 100%;
                    width: 280px;
                ul{
                    font-family: 'Oswald';
                    font-size: 20px;
                    font-weight: 700;
                    flex: 1;
                    width: 100%;
                    height: 100%;
                    display: flex;
                    align-items: center;
                    justify-content: space-between;
                   
                    li{
                        cursor: pointer;
                        list-style: none;
                         background: #414f6b;
                            height: 100%;
                            width: 100%;
                            &:hover{
                                background: #b0b4be;
                                color: #414f6b;
                                }
                        a{
                            background: #414f6b;
                            color: #b0b4be;  
                            height: 100%;
                            width: 100%;
                            display: flex;
                            align-items: center;
                            justify-content: center;
                            padding: 0 10px;
                            text-decoration: none;
                            &.active{
                                background: #b0b4be;
                                color: #414f6b;
                                text-decoration: underline;
                            }
                            &:hover{
                                background: #b0b4be;
                                color: #414f6b;
                                text-decoration: underline;
                                }
                        }
                    }
            }
        }
    }
}
.tab-content-bg{
     background: url("../assets/bg2.png") bottom/cover no-repeat;
        background-color: #414f6b;
        background-blend-mode: hard-light;
      min-height: 80vh;
      width: 100%;
      padding-bottom: 50px;
      section{
        height:100%;
        max-width: 900px;
        width: 100%;
        margin: auto;
        padding-top: 110px;
        // margin-right: 290px;
        position: relative;
        padding-left: 10px;
          div.container{
              background: rgba(255, 255, 255, 0.737); 
              max-width: 355px;
              width: 100%;
              min-height: 220px;
              height: auto;
              padding: 10px 40px;
          }
        }
    }
    #mountain2{
        .flex{&:nth-child(4){
            p{
                // color: #000;
            }
        }}
    }
    .hide{
        display: none;
        // transition: all ease-out .5s .5s;
        h4{
            font-family: 'Oswald';
            font-size: 32px;
            font-weight: 700;
            color: #414f6b;
            padding-bottom: 5px;
        }
            .flex{
                display: flex;
                justify-content: space-between;
                width: 100%;
                &:nth-child(4){
                    p{
                        // color: #b8b8b8;
                    }
                }
            }
            p{
                font-family: 'Lato';
                font-weight: 400;
                font-size: 16px;
                line-height: 1.5em;
            }
        }
    .active{
        &.show{
            display: block;
            /* padding: 0 10px; */
            // transition: all ease-out .5s .5s;
        }
    }
.accordion-container{
     background: url("../assets/bg2.png") bottom/cover no-repeat;
        background-color: #414f6b;
        background-blend-mode: hard-light;
      min-height: 50vh;
      width: 100%;
    padding-bottom: 100px;
    & div{
            text-align: left;
            font-size: 13px;
            font-family: 'Lato';
            font-weight: 300;
            line-height: 1.5em;
            background: #ffffff70;
            div{
                padding: 20px;
            }
    }
}
    
        @media screen and (max-width: 425px) {
            .hero-banner{
                    background: url("../assets/hero-banner.png") top/cover no-repeat, url("../assets/hero-text.png") top/cover no-repeat;
                    min-height: 100vh;
                    height: 100vh;
                    width: 100%;
                    .hero-text{
                    background: url("../assets/hero-text.png") top/cover no-repeat;
                    min-height: 100vh;
                    height: 100vh;
                    width: 100%;
                    }
                    }

            .tab-menu{
                .menu-flex{
                    ul{
                        // display: block!important;
                        // z-index:5;

                    }
                }
            }
            .climb-wrapper{
                height: auto;
                padding: 20px 0 30px;
                .climb-text{
                    .block{
                        flex-wrap: wrap;
                        p{
                            margin-left: 0;
                        }
                        h1{
                            span{
                                position: relative;
                                left: -25px;
                                bottom: 5px;
                            }
                        }
                    }
                }
            }
            #history{
                .history-text{
                    left: 0;
                    padding-left: 0;
                    .block{
                        h1{
                            text-align: center;
                        }
                    }
                    p{
                        background: #ffffff90;
                        padding: 30px;
                        margin-top: 30px;
                    }
                }
            }
         .accordion-container{
             & div{

                margin-bottom: 1px;
             }
        }
    }
          @media screen and (max-width: 600px) {
            .hero-banner {
                                background: url(/img/hero-banner.fd102435.png) center/cover no-repeat;
                                min-height: 140vw;
                                width: 100%;
                                padding-top: 100px;
                                position: relative;
                        }
                        .hero-banner .hero-text {
                            background: url(/img/hero-text.fdadb80f.png) top center/150% no-repeat;
                            min-height: 140vw;
                            width: 100%;
                            position: absolute;
                            right: -50%;
                            transform: translateX(-50%);
                        }
          }
  </style>
