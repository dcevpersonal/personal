<template>
    <div id = "PresentationDescriptionContainer">
        <article>
            <p>{{PresentationDescriptionItems[this.BaseSideBarMenuItemIdVar].title}}</p>
            <p>{{PresentationDescriptionItems[this.BaseSideBarMenuItemIdVar].name}}<span>...</span></p>
           
        </article>
         <p id = "PresentationDescriptionPageList">{{PresentationDescriptionPage}}/6</p>

    </div>
</template>

<script>


    export default {
        name: "BasePresentationDescription",
        data: function() {
            return {
                PresentationDescriptionItems: [
                {id: "0",title:"Архитектура", name: "Оригинальная архитектура жилого комплекса бизнес-класса «Первомайская» формирует современный стиль жизни"},
                {id: "1",title:"Благоустройство", name: "Запроектированные большие окна, которые пропускают много солнечного света, наполнят Ваши квартиры теплотой и уютом"},
                {id: "2",title:"Безопастность", name: "Современный двор европейского уровня — территория для детей, игр на свежем воздухе и вечерних"},
                {id: "3",title:"Инженерия", name: "Оригинальная архитектура жилого комплекса бизнес-класса «Первомайская» формирует современный стиль жизни"},
                {id: "4",title:"Инфраструктура", name: "Прекрасный вариант для тех, кто предпочитает жить в спокойном районе среди интеллигенции, но при этом чувствовать ритм мегаполиса"},
                {id: "5",title:"Транспортная доступность", name: "Жилой комплекс «Первомайска» расположен в престижном Академическом районе"}
                ],
                PresentationDescriptionPage: "1"
            }
        },
        
        props:[
            "BaseSideBarMenuItemIdVar"
        ],

        watch: {
            BaseSideBarMenuItemIdVar:
            function(BaseSideBarMenuItemIdVar) {
               this.PresentationDescriptionOnChange(BaseSideBarMenuItemIdVar);
               this.PresentationDescriptionPage = (parseInt(BaseSideBarMenuItemIdVar) + 1).toString();
            }

        },

        mounted: function() {
             this.PresentationDescriptionOnChange(0);
        },
        
        methods: {
            PresentationDescriptionOnChange:
            function PresentationDescriptionOnChange(id) {

                 var PresentationDescriptionContainerarcticle = document.querySelector("#PresentationDescriptionContainer > article");
                 var PresentationDescriptionContainerarcticleBox = document.querySelector("#PresentationDescriptionContainer > article > p > span");


                 if(this.PresentationDescriptionItems[id].name.length > 90) {
                     PresentationDescriptionContainerarcticleBox.style.opacity = "1";
                 }
                 

                 else {
                     PresentationDescriptionContainerarcticleBox.style.opacity = "0";
                 }


                if(id == 0) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(-200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


                else if(id == 1) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


               else if(id == 2) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(-200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


               else if(id == 3) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


               else if(id == 4) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(-200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


               else if(id == 5) {
                    PresentationDescriptionContainerarcticle.style.transform = "translateY(200px)";
                    PresentationDescriptionContainerarcticle.style.opacity = "0";
                    PresentationDescriptionContainerarcticle.style.transition = "none";
                    setTimeout(()=>{PresentationDescriptionContainerarcticle.style.transform = "translateY(0px)",PresentationDescriptionContainerarcticle.style.opacity = "1",PresentationDescriptionContainerarcticle.style.transition = "all 0.3s ease"},100);
               }


            }
            

        },

    }


</script>


<style scoped>


#PresentationDescriptionContainer {
    display: flex;
    width: 50%;
    height: 100%;
    background: #F0F0F0;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}


#PresentationDescriptionContainer > article {
    width: 435px;
    height: fit-content;
    font-size: 20px;
    text-align: left;
    transition: all 0.3s ease;
    opacity: 0;
}


#PresentationDescriptionContainer > article > p:nth-child(1){
    font-family: Gilroy;
    font-size: 44px;
    font-weight: 800;
    letter-spacing: -0.03px;
}


#PresentationDescriptionContainer > article > p:nth-child(2){
    font-family: Roboto;
    font-size: 18px;
    line-height: 30px;
    letter-spacing: -0.02px;
    margin-top: 40px;
}


#PresentationDescriptionContainer > article > p > span{
    position: absolute;
    display: inline-block;
    width: 28px;
    height: 28px;
    text-align: center;
    vertical-align: middle;
    line-height: normal;
    color: #F0F0F0;
    background: #262525;
    margin-left: 10px;
}

#PresentationDescriptionPageList {
    position: relative;
    width: 435px;
    font-family: Gilroy_Light;
    font-weight: 300;
    font-size: 17px;
    line-height: 20px;
    top: 150px;
}


@media only screen and (max-width: 1300px) {


#PresentationDescriptionContainer {
    display: flex;
    width: 100%;
    height: 100%;
    background: #F0F0F0;
    flex-direction: column;
    margin: 0;
    align-items: center;
    justify-content: center;
}


#PresentationDescriptionPageList {
    top: 70px;
}


}


</style>