<template>
    <div class="wrapper">
        <footer>
            <div class="logo">
                <div class="img"></div>
                <span class="img-overlay"></span>
                <div class="la">
                <h4>LOS ANGELES </h4>
                <h4>MOUNTAINS </h4>
                </div>
                </div>
            <div class="copy">
                <p>COPYRIGHT 2016. ALL RIGHTS RESERVED.</p>
            </div>
        </footer>
    </div>
</template>


<style lang="scss" scoped>
.wrapper{
    width: 100%;
    height: 50px;
    padding: 10px 0;
    background-color: #414f6b;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    position: relative;
    footer{
        max-width: 1000px;
        width: 100%;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        // margin: 0 5%;
        color: #63769d;
        .copy{margin-right: 3.2%;
        p{font-family: 'Lato'; font-size: 12px; font-weight: 700;font-style: italic;}
        }
        .logo{
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            .img{background: url('../assets/logo.png') center/contain no-repeat; background-color: #414f6b; background-blend-mode: overlay; width:35px;height: 35px;}
            // .img-overlay{display:block;position:absolute;left:0;bottom:0;top:0;width:30px;height: 30px;border-radius: 50%;background-color: #53699390;}
            .la{
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                padding-left: 5px;
                line-height: 18px;
                h4{
                    font-family: var(--font-Bebas);
                    font-size: 21px;
                    font-weight: 200;
                }
                h4:nth-child(2){font-size: 23px;letter-spacing: .4px;}
            }
        }
    }
}
// .wrapper-overlay{
//     position: absolute;
//     bottom: 0;
//     left: 0;
//     width: 100%;
//     height: 50px;
//     padding: 10px 0;
//     background-color: #414f6b;
// }
    @media screen and (max-width: 425px) {
           .wrapper footer{
                margin: 0;
                .copy{
                    margin-right: 3%;
                    p{
                        font-size: 10px;
                    }
                }
            }           

    }
</style>