<template>
    <div id = "PresentationSlideShowContainer">
        <div id = "PresentationSlideShowContainerImageTop"></div>
        <div id = "PresentationSlideShowContainerImageBottom"></div>
    </div>
</template>

<script>
    export default {
        name: "BasePresentationSlideShow",
        props:[
            "BaseSideBarMenuItemIdVar"
        ],

        data:function() {
            return {
                PresentationSlideShowSelectedItem: "0"
            }
        },

        mounted: function() {
            this.PresentationSlideShowOnChange(0);
        },

        watch: {
            BaseSideBarMenuItemIdVar:
            function(BaseSideBarMenuItemIdVar) {
            this.PresentationSlideShowOnChange(BaseSideBarMenuItemIdVar);
            }
        },

        methods: {
            PresentationSlideShowOnChange:
            function PresentationSlideShowOnChange(id) {
              
               var PresentationSlideShowContainerImageTop = document.getElementById("PresentationSlideShowContainerImageTop")
               var PresentationSlideShowContainerImageBottom = document.getElementById("PresentationSlideShowContainerImageBottom")
                
                if(getComputedStyle(PresentationSlideShowContainerImageTop).height == "0px") {
                    PresentationSlideShowContainerImageTop.style.backgroundImage = 'url(' + require("../../../assets/Illustrations/Illustration-" + (parseInt(id) +  1) + ".png") + ')';
                    PresentationSlideShowContainerImageTop.style.transition = "all 0.8s ease";
                    PresentationSlideShowContainerImageTop.style.height = "100%";
                    PresentationSlideShowContainerImageBottom.style.transition = "none";
                    PresentationSlideShowContainerImageBottom.style.height = "0";
                }

                else if (getComputedStyle(PresentationSlideShowContainerImageBottom).height == "0px") {
                    PresentationSlideShowContainerImageBottom.style.backgroundImage = 'url(' + require("../../../assets/Illustrations/Illustration-" + (parseInt(id) +  1) + ".png") + ')';
                    PresentationSlideShowContainerImageBottom.style.transition = "all 0.8s ease";
                    PresentationSlideShowContainerImageBottom.style.height = "100%";
                    PresentationSlideShowContainerImageTop.style.transition = "none";
                    PresentationSlideShowContainerImageTop.style.height = "0"
                    
                }
            },
        }
    }
    

</script>

<style scoped>


#PresentationSlideShowContainer {
    position: relative;
    display: flex;
    width: 50%;
    height: 100%;
    background: #F0F0F0;
    align-items: flex-start;
    justify-content: flex-start;
}


#PresentationSlideShowContainerImageTop {
    position:absolute;
    position: relative;
    width: 100%;
    height: 100%;
    transition: all 0.8s ease;

}


#PresentationSlideShowContainerImageBottom {
    position:absolute;
    width: 100%;
    height: 0;
    transition: all 0.8s ease;
}

@media only screen and (max-width: 1200px) {

#PresentationSlideShowContainer {
    position: relative;
    display: flex;
    width: 100%;
    height: 100%;
    background: no-repeat center center fixed;
    background-size: cover;
    margin: 0;
    padding: 0;
    align-items: flex-start;
    justify-content: flex-start;
}


#PresentationSlideShowContainer > div {
    width: 100%;
    background: no-repeat center center fixed;
    background-size: cover;
    margin: 0;
    padding: 0;
}


}

</style>