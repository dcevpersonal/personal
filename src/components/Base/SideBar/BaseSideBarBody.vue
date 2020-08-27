<template>
        <div id = "SideBarBackground">
            <BaseSideBarMenu @BaseSideBarMenuItemId = "BaseSideBarMenuItemId"/>
         </div>
</template>

<script>
import BaseSideBarMenu from "./BaseSideBarMenu"
    export default {
        name: "BaseSideBarBody",
        components: { 
            BaseSideBarMenu
            },
        methods: {
            BaseSideBarMenuItemId(BaseSideBarMenuItemId) {
                this.$emit("BaseSideBarMenuItemId",BaseSideBarMenuItemId);
            }
        }
    }
</script>

<style scoped>


#SideBarBackground {
    position: absolute;
    display: flex;
    width: 384px;
    height: 100%;
    z-index: 1;
}


@media only screen and (max-width: 1300px) {

    #SideBarBackground {
        width: 100%;
        height: 600px;
        margin-top: 1260px;
        align-items: center;
        justify-content: center;
    }

}

</style>