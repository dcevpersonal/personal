<template>
    <header id = "HeaderBackground">
        <div id = "HeaderBodyLeftRectangle"></div>
        <div id = "HeaderBodyRightRectangle"><img src="../../../assets/Icons/BaseHeaderBodyIcon_1.svg"/></div>
     <BaseHeaderMenu />
    </header>
</template>

<script>
import BaseHeaderMenu from "./BaseHeaderMenu"

    export default {
        name: "BaseHeaderBody",
        components: {
            BaseHeaderMenu
        }
    }
</script>

<style scoped>


#HeaderBackground {
    display: flex;
    position: absolute;
    width: 100%;
    height: 60px;
    justify-content: center;
    align-items: center;
    z-index: 2;
}

#HeaderBodyLeftRectangle {
    position: absolute;
    height: 70px;
    width: 70px;
    left: 24px;
    top: 24px;
    background: #262525;
}


#HeaderBodyRightRectangle {
    position: absolute;
    display: flex;
    height: 70px;
    width: 70px;
    right:24px;
    top: 24px;
    align-items: center;
    justify-content: center;
    background: #262525;
}


#HeaderBodyRightRectangle > img {
    width: 27px;
    height: 27px;
}

@media only screen and (max-width: 1300px) {


#HeaderBackground { 
    width: 100%;
    margin: 0;
}


}

</style>