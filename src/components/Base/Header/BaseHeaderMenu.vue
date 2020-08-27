<template>
<div id = "headerMenuContainer">
    <ul id = "headerMenuList" >
        <li v-for="item in HeaderMenuItems" v-bind:key="item.id" v-on:click = "ClickHeaderItem(item.id)" v-on:mouseover = "HoverHeaderItemOn(item.id)"  v-on:mouseout = "HoverHeaderItemOff()"  v-bind:id = "'headerMenuItem' + item.id">{{item.name}}<span></span></li>
    </ul>
</div>
</template>

<script>
    export default {
        name: "BaseHeaderheaderMenu",

        data: function() {
            return {
                SelectedHeaderItem: "1",
                HeaderMenuItems: [

                    {id:"0", name: "Первомайская"},
                    {id:"1",name:"О Комплексе"},
                    {id:"2",name:"Особенности"},
                    {id:"3", name:"Пентхаус"},
                    {id:"4", name:"Выбрать Квартиру"},
                    {id:"5", name:"8 888 888 88 88"}
                    
                ]
            }
        },

        mounted: function() {
           setTimeout(()=>{this.ClickHeaderItem("1")},100);
        },

        methods: {
            
            ClickHeaderItem:
            function ClickHeaderItem(id) {

                if(id != 5 && id != 0) {
                    var SelectedHeaderItemBorder = document.querySelector("#headerMenuItem"+ this.SelectedHeaderItem + " > span");
                    var CurrentHeaderItemBorder = document.querySelector("#headerMenuItem"+ id + " > span");
                    var CurrentHeaderItem = document.getElementById("headerMenuItem" + id);
                    SelectedHeaderItemBorder.style.background = "rgba(216, 143, 94, 0)";
                    this.SelectedHeaderItem = id;
                    CurrentHeaderItemBorder.style.background = "rgba(216, 143, 94, 1)";
                    CurrentHeaderItemBorder.style.width= CurrentHeaderItem.offsetWidth + "px";                  
                }

            },
            
            HoverHeaderItemOn: 
            function HoverHeaderItemOn(id) {

                if(id != 5 && id != 0) {
                    var SelectedHeaderItemBorder = document.querySelector("#headerMenuItem"+ this.SelectedHeaderItem + " > span");
                    var CurrentHeaderItemBorder = document.querySelector("#headerMenuItem"+ id + " > span");
                    var CurrentHeaderItem = document.getElementById("headerMenuItem" + id)
                    var SelectedHeaderItem = document.querySelector("#headerMenuItem"+ this.SelectedHeaderItem);
                    var distance = (CurrentHeaderItem.offsetLeft - SelectedHeaderItem.offsetLeft);

                    if(distance < 0 ) {
            
                        SelectedHeaderItem.style.direction = "rtl";
                        SelectedHeaderItemBorder.style.direction = "rtl";
                        SelectedHeaderItemBorder.style.width = Math.abs(distance)+ SelectedHeaderItem.offsetWidth + "px"; 
                        CurrentHeaderItem.style.direction = "ltr";
                        CurrentHeaderItemBorder.style.direction = "ltr";
                        CurrentHeaderItemBorder.style.width = Math.abs(distance) + SelectedHeaderItem.offsetWidth + "px"; 
                    } 

                    else  if (distance > 0 ){
                        SelectedHeaderItem.style.direction = "ltr";
                        SelectedHeaderItemBorder.style.direction = "ltr";
                        SelectedHeaderItemBorder.style.width = distance + CurrentHeaderItem.offsetWidth + "px"; 
                        CurrentHeaderItem.style.direction = "rtl";
                        CurrentHeaderItemBorder.style.direction = "rtl";
                        CurrentHeaderItemBorder.style.width = Math.abs(distance) + CurrentHeaderItem.offsetWidth + "px"; 
                    }

                    else {
                        SelectedHeaderItemBorder.style.width = SelectedHeaderItem.offsetWidth + "px"; 
                    }

                    
                }

            },

            HoverHeaderItemOff:
            function HoverHeaderItemOff() {
                var SelectedHeaderItemBorder = document.querySelector("#headerMenuItem"+ this.SelectedHeaderItem + " > span");
                var SelectedHeaderItem = document.querySelector("#headerMenuItem"+ this.SelectedHeaderItem);
                SelectedHeaderItemBorder.style.width = SelectedHeaderItem.offsetWidth + "px";
            }

        }
    }

</script>

<style scoped>


#headerMenuContainer {
    display: flex;
    width: 100%;
    height: 100%;
    align-items: center;
    justify-content: center;
}


#headerMenuList {
    display: flex;
    width: 100%;
    height: fit-content;
    font-family: Gilroy;
    font-weight: 800;
    font-size: 12px;
    line-height: 15px;
    letter-spacing: 0.8px;
    text-transform: uppercase;
    color: #262525;
    list-style: none;
    align-items: center;
    justify-content: center;
    flex-direction: row;
    margin: 0;
    padding: 0;
    
}


#headerMenuList > li {
    display: inline-block;
    cursor: pointer;
    margin-left: 56px;
}


#headerMenuList > li > span {
    display: block;
    position: absolute;
    content: "";
    transition: width 0.3s ease;
    height: 4px;
    background: rgba(216, 143, 94, 0);
    z-index: -1;
}

#headerMenuList > li:nth-child(1) {
    font-size: 17px;
    cursor: default;
    letter-spacing: 0.3px;
    margin-left: 0;
    margin-right: auto;
    margin-left: 120px;
}

#headerMenuList > li:nth-child(2) {
    margin: 0;
}


#headerMenuList > li:nth-child(6) {
    font-size: 17px;
    cursor: default;
    letter-spacing: 0.3px;
    margin-left: auto;
    margin-right: 8%;
}


@media only screen and (max-width: 1200px) {


#headerMenuList {
    justify-content: flex-start;
}


#headerMenuList > li:nth-child(n+1) {
    display: none;
    margin: 0;
}


#headerMenuList > li:nth-child(6) {
    display: block;
    margin-left: auto;
    margin-right: 10%;
}


}

</style>