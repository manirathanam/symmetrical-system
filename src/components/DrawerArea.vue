<template>
    <div class="drawer-area">
        <img class="company-logo" src="@/assets/aspire-logo.png" alt="aspire logo"  />
        <div class="company-status">Trusted way of banking for 3,000+ SMEs and startups in Singapore</div>
        <nav-menu></nav-menu>
    </div>
</template>

<script>
import NavMenu from './NavMenu.vue'
    export default {
        name:"DrawerArea",
        components:{NavMenu}
    }
</script>

<style lang="scss" scoped>

@import "@/styles/_variables.scss";

.drawer-area {
    background-color:$bg-primary-dark;
    width:340px;
    height:calc(100% - 0px);
    padding:48px;
    box-sizing: border-box;
    overflow: auto;

    img {
        width: 125px;
        height: 35px;
    }
}

.company-status {
    font-family: $text-family;
    color:$text-white;
    margin-top: 20px;
    font-size: 15px;
    line-height: 20px;
    opacity:31%;
}

</style>
