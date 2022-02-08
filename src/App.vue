<template>
  <div id="nav" :class="{scrolled: _scrolled_nav}">
    <div class="navbar">
        <div class="logo">
           <router-link :to="{name: 'Home', hash: '#hero'}">
          <img src="./assets/logo.png" width="35" height="35" alt="">
          </router-link>
            <div class="la">
                <h4>LOS ANGELES </h4>
                <h4>MOUNTAINS </h4>
            </div>
        </div>
        <ul class="links-wrapper">
            <li class="links"> 
            <router-link :to="{name: 'Home', hash: '#history'}">01. HISTORY</router-link>
              </li>
            <li class="links"> 
              <router-link :to="{name: 'Home', hash: '#team'}">02. TEAM</router-link>
            </li>
        </ul>
   </div>
  </div>
  <router-view/>
</template>

<script>
import {onMounted, ref} from 'vue'
  export default{
    setup(){
    const _scrolled_nav = ref(null)

    
      onMounted(() => { 

        window.addEventListener('scroll', updateScroll)
        })
      const updateScroll = () => {
      const scrollPos = window.scrollY
      scrollPos > 50 ? _scrolled_nav.value = true : _scrolled_nav.value = false
      }
    return{ onMounted,updateScroll, _scrolled_nav }
    }
  }
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Oswald:wght@200;300;400;500;600;700&display=swap');

:root{
--font-Bebas: 'Bebas Neue', cursive;
--font-Lato: 'Lato', sans-serif; 
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: var(--font-Lato);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
  position: relative;
}

#nav {
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 15px;
  position: fixed;
  z-index: 99;
  left: 50%;
  top: 0;
  transform: translateX(-50%);
  background-color: transparent;
  transition: all .5s ease-in-out;
    &.scrolled{
      background-color: white;
      .navbar{
        .logo{
          .la{
                display: flex;
              }
        }
      }
      a{
        color: #414f6b;
         &.router-link-exact-active {
           // color: rgb(14, 14, 14);
           color: #414f6b;
    }
  }
}
  .navbar{
    max-width: 1000px;
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    // margin: 0 5%;
    .logo{
       display: flex;
            justify-content: center;
            align-items: center;
            padding-left: 50px;
       .la{
                display: none;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                padding-left: 5px;
                line-height: 18px;
                h4{
                    font-family: var(--font-Bebas);
                    font-size: 21px;
                    font-weight: 200;color:#4d4d4d;
                }
                h4:nth-child(2){font-size: 23px;letter-spacing: .4px;color:#414f6b}
            }
    }
  }
  ul{
    width: 250px;
    display: flex;
    align-items: center;
    text-align: center;
      li{
        list-style: none;
        text-decoration: none;
        padding: 0 2%;
        flex: 1;
    }
  }
  a {
    font-weight: 700;
    color: #fff;
    font-family: var(--font-Lato);
    font-style: italic;
    font-size: 12px;
    letter-spacing: 1px;
    &.router-link-exact-active {
      color: #eaeaea;
    }
  }
}

 @media screen and (max-width: 1000px) {
   #nav{
    .navbar{
    .logo{
            padding-left: 0;
    }
    }
   }
 }

  @media screen and (max-width: 425px) {
    #nav{
     ul{
      width: 200px;
      text-align: right;
      li{
        a{
          // font-size: 10px;
        }
      }
     }
    }
  }
  #nav.scrolled{
    .navbar{
      .logo{
        .la{
          display: none;
        }
      }
    }
  }
</style>
