<template>
  <div class="payment-area">
    <label class="balance-label">Available balance</label>
    <div class="amount-container flex">
      <div class="flex">
        <span class="currency">$$</span>
        <span class="amount bold">3,000</span>
      </div>
      <div class="new-card bg-primary flex">
        <div class="flex">
          <img src="@/assets/box.svg" height="16" width="16" />
          <label class="bold">New Card</label>
        </div>
      </div>
    </div>
    <div class="tab-header flex ">
      <label class="bold">My debit cards</label>
      <label class="text-disabled bold">All company cards</label>
    </div>
    <div class="payment-card flex flex-start-col">
      <debit-card></debit-card>
      <payment-history ></payment-history>
    </div>
  </div>
</template>

<script>
import DebitCard from './DebitCard.vue';
import PaymentHistory from './PaymentHistory.vue';
export default {
  name: "PaymentArea",
  components:{
      DebitCard,
    PaymentHistory,
  }
};
</script>
<style lang="scss" scoped>
@import "@/styles/_variables.scss";

.payment-area {
  font-family: $text-family;

  .balance-label {
    font-size: 14px;
    line-height: 16px;
  }

  .amount-container {
    margin-top: 10px;
    justify-content: space-between;

    .currency {
      color: $text-white;
      border-radius: $border-radius-sm;
      background-color: $bg-accent;
      padding: 2px 12px 2px 12px;
      margin-right: 12px;
    }

    .amount {
      font-size: 36px;
    }

    .new-card {
      padding: 8px 12px 8px 12px;
      height: 36px;
      border-radius: $border-radius-sm;

      img {
        margin-right: 8px;
      }
    }
  }

  .tab-header {
    height: 24px;
    margin-top: 34px;
    :first-child {
      margin-right: 32px;
      border-bottom: 2px solid #23cefd;
    }
  }

  .payment-card {
    margin-top: 16px;
    box-shadow: 0px 2px 12px #00000014;
    padding: 32px 40px 32px 40px;

  }
}


</style>

<style>
@media screen and (max-width: 1130px) {
  .payment-card.flex.flex-start-col {
    flex-direction: column;
  }
}


@media screen and (max-width: 900px) {
  .payment-card.flex.flex-start-col {
    flex-direction: column;
  }

  .nav-menu {
    display: flex;
    justify-content: space-around;
  }

  .drawer-area {
    position: absolute;
    bottom:0px;
    width:100% !important;
    height:100px !important;
    padding:8px !important;
  }
  .company-status, .company-logo {
    display:none;
  }

  .nav-menu-item {
    flex-direction: column;
    margin-top:0px !important
  }

  .content-area {
    width:100% !important;
  }
}


</style>
