<template>
    <div id = "sidebarMenuContainer">
        <ul id="sidebarMenuList">
            <li v-for="sidebarmenuitem in SidebarMenuItems" v-bind:key="sidebarmenuitem.id" v-on:click = "ClickSideBarItem(sidebarmenuitem.id)" v-on:mouseover = "HoverSideBarItemOn(sidebarmenuitem.id)" v-on:mouseout = "HoverSideBarItemOff(sidebarmenuitem.id)" v-bind:id = "'sidebarMenuItem' + sidebarmenuitem.id">{{sidebarmenuitem.name}}<span></span></li>    
        </ul>
    </div>
</template>

<script>
    export default {
        name: "BaseSideBarMenu",
        data:function() {
            return {
                SelectedSideBarItem: "0",
                SidebarMenuItems: [
                    {id:"0",name: "Архитектура"},
                    {id:"1",name: "Благоустройтсва"},
                    {id:"2",name: "Безопасность"},
                    {id:"3",name: "Инженерия"},
                    {id:"4",name: "Инфраструктура"},
                    {id:"5",name: "Транспортная Доступность"},
                ]
            }
        },

        mounted: function() {
            setTimeout(()=>{this.ClickSideBarItem("0")},100);
        },

        methods: {
            ClickSideBarItem:
            function ClickSideBarItem(id) {
                    var SelectedSideBarItemBorder = document.querySelector("#sidebarMenuItem"+ this.SelectedSideBarItem + " > span");
                    var CurrentSideBarItemBorder = document.querySelector("#sidebarMenuItem"+ id + " > span");
                    var SelectedSideBarItem = document.querySelector("#sidebarMenuItem"+ this.SelectedSideBarItem);
                    var CurrentSideBarItem = document.getElementById("sidebarMenuItem" + id);
                    SelectedSideBarItemBorder.style.background = "rgba(235, 216, 204,0)";
                    SelectedSideBarItemBorder.style.width= "0";
                    SelectedSideBarItem.style.fontWeight = "300";
                    SelectedSideBarItem.style.color= "#505050";
                    SelectedSideBarItem.style.lineHeight = "15px";
                    SelectedSideBarItem.style.transform = "scale(1)";
                    this.SelectedSideBarItem = id;
                    CurrentSideBarItemBorder.style.background = "rgba(235, 216, 204,1)";
                    CurrentSideBarItemBorder.style.width= CurrentSideBarItem.offsetWidth + 10 +"px"; 
                    CurrentSideBarItem.style.fontWeight = "700";
                    CurrentSideBarItem.style.color = "#262525";
                    CurrentSideBarItem.style.lineHeight = "16px";
                    CurrentSideBarItem.style.transform = "scale(1.2)";
                    this.$emit("BaseSideBarMenuItemId",this.SelectedSideBarItem);
             },

            HoverSideBarItemOn: 
            function HoverSideBarItemOn(id) {
                    var CurrentSideBarItem = document.getElementById("sidebarMenuItem" + id);
                    var CurrentSideBarItemBorder = document.querySelector("#sidebarMenuItem"+ id + " > span");
                    CurrentSideBarItemBorder.style.background = "rgba(235, 216, 204,1)";
                    CurrentSideBarItemBorder.style.width = CurrentSideBarItem.offsetWidth + 10 +"px";
            },

            HoverSideBarItemOff:
            function HoverSideBarItemOff(id) {
                    var SelectedSideBarItemBorder = document.querySelector("#sidebarMenuItem"+ this.SelectedSideBarItem + " > span");
                    var CurrentSideBarItemBorder = document.querySelector("#sidebarMenuItem"+ id + " > span");
                    var SelectedSideBarItem = document.querySelector("#sidebarMenuItem"+ this.SelectedSideBarItem);
                    CurrentSideBarItemBorder.style.background = "rgba(235, 216, 204,0)";
                    CurrentSideBarItemBorder.style.width = "0";
                    SelectedSideBarItemBorder.style.background = "rgba(235, 216, 204,1)";
                    SelectedSideBarItemBorder.style.width= SelectedSideBarItem.offsetWidth + 10 +"px"; 
            }


        }
    }


</script>

<style scoped>


#sidebarMenuContainer {
    display: flex;
    width: 100%;
    height: 100%;
    align-items: center;
    justify-content: center;
}


#sidebarMenuList {
    display: flex;
    width: fit-content;
    height: fit-content;
    font-family: Roboto;
    font-weight: 300;
    font-size: 13px;
    line-height: 15px;
    letter-spacing: 0.57px;
    text-transform: uppercase;
    color: #505050;
    list-style: none;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    margin: 0;
    padding: 0;
}


#sidebarMenuList > li {
    display: inline-block;
    cursor: pointer;
    transition: transform 0.3s ease;
    margin-top: 32px;
    text-align: left;
}


#sidebarMenuList > li > span {
    display: block;
    position: absolute;
    content: "";
    transition: all 0.3s ease;
    height: 9px;
    margin-top: -7px;
    margin-left: -5px;
    background: rgba(235, 216, 204,0);
    z-index: -1;
}

@media only screen and (max-width: 1200px) { 

#sidebarMenuContainer {
    display: flex;
    width: 100%;
    height: fit-content;
    align-items: center;
    justify-content: center;
}

#sidebarMenuList {
    align-items: center;
}


}

</style>