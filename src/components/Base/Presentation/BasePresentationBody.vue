<template>
    <main id = "PresintationBackground">
        <div id = "PresentationContainer">
            <BasePresentationDescription v-bind:BaseSideBarMenuItemIdVar = "BaseSideBarMenuItemIdVar" />
            <BasePresentationSlideShow v-bind:BaseSideBarMenuItemIdVar = "BaseSideBarMenuItemIdVar" />
        </div>
    </main>
</template>

<script>

import BasePresentationDescription from "./BasePresentationDescription";
import BasePresentationSlideShow from "./BasePresentationSlideShow";

    export default {
        name: "BaseMainPresentationBody",
        components: {
            BasePresentationDescription,
            BasePresentationSlideShow
        },

        props: [
             "BaseSideBarMenuItemIdVar"
             ]
    }
</script>

<style scoped>

#PresintationBackground {
    width: 100%;
    height: 100%;
}

#PresentationContainer {
    display: flex;
    width: calc(100% - 444px);
    height: calc(100% - 120px);
    flex-direction: row;
    margin-left: 384px;
    margin-top: 60px;
}


@media only screen and (max-width: 1300px) {
 

 #PresentationContainer {
    width: 100%;
    height: 1200px;
    flex-direction: column-reverse;
    margin: 0;
    margin-top: 60px;
}


}

</style>