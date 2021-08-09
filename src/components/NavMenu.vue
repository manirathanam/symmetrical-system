<template>
    <div class="nav-menu">

      
        <div class="nav-menu-item" v-for="item in items" :key="item.iconName">
            <img class="nav-menu-item-icon" :src="item.icon" :alt="item.iconName">
            <label class="nav-menu-item-label" :class="item.active ? 'active' :''">{{item.label}}</label>
        </div>
        
    </div>
</template>

<script>
    export default {
        name:"NavMenu",
        setup(){
            let items = [
                { 'label':"Home",'icon':require('@/assets/Home.svg'),'iconName':'Home'},
                { 'label':"Cards",'icon':require('@/assets/Card.svg'),'iconName':'Card','active':true},
                { 'label':"Payments",'icon':require('@/assets/Payments.svg'),'iconName':'Payments'},
                { 'label':"Credit",'icon':require('@/assets/Credit.svg'),'iconName':'Credit'},
                { 'label':"Settings",'icon':require('@/assets/Account.svg'),'iconName':'Settings'},
            ];
            return {items};
        }
    }
</script>

<style lang="scss" scoped>

@import "@/styles/_variables.scss";

.nav-menu {
    margin-top:20px;
    font-family: $text-family;
    font-size:16px;
    line-height: 32px;
    color: $text-white;

    .nav-menu-item {
        display: flex;
        align-items: center;
        height: 24px;
        margin-top: 60px;

        .nav-menu-item-label {
            margin-left:16px;
            &.active{
                color : $text-accent;
                font-weight: bold;
            }
        }

        .nav-menu-item-icon{
            height: 24px;
            width: 24px;
        }

    }
}

</style>