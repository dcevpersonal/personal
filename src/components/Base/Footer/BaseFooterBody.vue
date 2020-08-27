<template>
    <footer id = "FooterBackground">
       <p>Разработано в MST      |      2018</p>
       <p> Prototype was made by Danil Lazarev-2020</p>
    </footer>
</template>

<script>
    export default {
        name: "BaseFooterBody"
    }
</script>

<style scoped>


#FooterBackground {
    display: flex;
    position: absolute;
    width: 100%;
    height: 60px;
    justify-content: flex-start;
    align-items: center;
    bottom: 0;
    z-index: 2;
}


#FooterBackground > p {
    font-family: Gilroy_Light;
    font-weight: 300;
    font-size: 13px;
    color: #505050;
    text-transform: uppercase;
    margin-left: 60px;
    line-height: 15px;
    letter-spacing: 0.17px;


}


#FooterBackground > p:nth-child(2) {
    margin-left: auto;
    margin-right: 60px;


}




@media only screen and (max-width: 1300px) {


#FooterBackground {
    top: 1800px;

}

}

</style>