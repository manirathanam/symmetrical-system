<template>
    <div class="symmertic-section">
          <drawer-area></drawer-area>
          <div class="content-area">
              <payment-area></payment-area>
          </div>
    </div>
</template>

<script>
import DrawerArea from './DrawerArea.vue'
import PaymentArea from './PaymentArea.vue'
    export default {
  components: { DrawerArea, PaymentArea },
        name:"SymmetricSection"
    }
</script>

<style lang="scss">

body {
    margin:0px;
    height:100%;
    width:100%;
}

.symmertic-section{
    position: absolute;
    height: 100%;
    width: 100%;
    display: flex;
}

.content-area {
    padding: 60px;
    width: calc(100% - 340px);
    box-sizing: border-box;
    overflow:auto;
    height:100%;
}

</style>