<template>
    <div id= "Base">
        <BaseSideBarBody @BaseSideBarMenuItemId = "BaseSideBarMenuItemId"/>
        <BaseHeaderBody />
        <BasePresentationBody v-bind:BaseSideBarMenuItemIdVar = "BaseSideBarMenuItemIdVar"/>
        <BaseFooterBody />
    </div>
</template>


<script>
import BaseHeaderBody from "./Header/BaseHeaderBody";
import BaseSideBarBody from "./SideBar/BaseSideBarBody";
import BasePresentationBody from "./Presentation/BasePresentationBody";
import BaseFooterBody from "./Footer/BaseFooterBody";

    export default {
        name: "Base",
        components: {
            BaseHeaderBody,
            BaseSideBarBody,
            BasePresentationBody,
            BaseFooterBody

        },

        data: function() {
            return {
                BaseSideBarMenuItemIdVar: "0"
            }
        },

        methods: {
            BaseSideBarMenuItemId(BaseSideBarMenuItemId) {
                this.BaseSideBarMenuItemIdVar = BaseSideBarMenuItemId
            }

        }
    }
</script>

<style scoped>

#Base {
    display: flex;
    position: relative;
    width: 100%;
    height: 100%;
    z-index: 0;
}

</style>