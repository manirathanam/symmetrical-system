<template>
  <div class="payment-history">
    <div class="accordion-container">
      <div class="accordion-header flex">
        <div class="header flex">
          <img class="" src="@/assets/Card-detail.svg" height="24" width="24" />
          <label class="text-primary">Card details</label>
        </div>
        <div class="close-icon">
          <img src="@/assets/down-arrow.svg" height="20" width="20" />
        </div>
      </div>
    </div>
    <div class="accordion-container">
      <div class="accordion-header flex">
        <div class="header flex">
          <img
            class=""
            src="@/assets/recent-transaction.svg"
            height="24"
            width="24"
          />
          <label class="text-primary">Recent transactions</label>
        </div>
        <div class="close-icon">
          <img src="@/assets/up-arrow.svg" height="20" width="20" />
        </div>
      </div>
      <div class="accordion-body">
        <div
          class="transaction-detail flex flex-start-col"
          v-for="(item,index) in items"
          :key="index"
        >
          <div
            class="transation-image"
            :style="{ 'background-color': item.backgroundColor }"
          >
            <img :src="item.icon" height="16" width="16" />
          </div>
          <div class="merchandise-detail flex flex-column flex-start-col">
            <label class="merchandise-name bold">{{ item.companyName }}</label>
            <label class="transaction-date text-disabled">{{
              item.date
            }}</label>
            <div class="transaction-card-info flex">
              <img
                class="transation-card-image"
                src="@/assets/Payments.svg"
                height="10"
                width="10"
              />
              <label class="transaction-card-label">{{ item.cardInfo }}</label>
            </div>
          </div>
          
          <div
            class="transation-amount"
            :class="item.debited ? 'text-accent' : ''"
          >
            <label class="bold">{{ item.amount }}</label>
            <label class=" bold text-disabled"> &nbsp;></label>
          </div>
        </div>
      <div class="view-all">
          <label class="text-accent bold">View all card transactions</label>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PaymentHistory",
  setup() {
    let items = [
      {
        companyName: "Hamleys",
        backgroundColor: "#009DFF1A",
        date: "20 May 2020",
        cardInfo: "Refund on debit card",
        debited: true,
        amount: "+ S$ 150",
        icon:require("@/assets/file-storage.svg")
      },
      {
        companyName: "Hamleys",
        backgroundColor: "#00D6B51A",
        date: "20 May 2020",
        cardInfo: "Charged to debit card",
        debited: false,
        amount: "- S$ 150",
        icon:require("@/assets/flights.svg")
      },
      {
        companyName: "Hamleys",
        backgroundColor: "#F251951A",
        date: "20 May 2020",
        cardInfo: "Charged to debit card",
        debited: false,
        amount: "- S$ 150",
        icon:require("@/assets/megaphone.svg")
      },
      {
        companyName: "Hamleys",
        backgroundColor: "#009DFF1A",
        date: "20 May 2020",
        cardInfo: "Refund on debit card",
        debited: false,
        amount: "- S$ 150",
        icon:require("@/assets/file-storage.svg")
      },
    ];

    return { items };
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/_variables.scss";

.payment-history {
  width: 100%;
  margin-top: 8px;

  .accordion-container {
    .accordion-header {
      margin-top: 24px;
      background-color: $bg-primary-soft;
      border-radius: 8px;
      justify-content: space-between;
      padding: 24px;

      .header {
        img {
          margin-right: 12px;
        }
      }

      .close-icon {
      }
    }
    .accordion-body {
      border: 1px solid #f0f0f0;
      padding: 24px 24px 24px 24px;
      border-radius: 8px;

      .transaction-detail {
          margin-top: 32px;
      }

      .transaction-detail:first-child {
          margin-top: 0px;
      }

      .transation-image {
        padding: 16px;
        margin-right: 12px;

        border-radius: 50%;
        background-color: #009dff1a;
      }

      .transation-card-image {
        padding: 6px 7px 6px 7px;
        margin-right: 8px;
        border-radius: 40%;
        background-color: $bg-primary;
      }

      .transaction-date {
        margin-top: 4px;
      }

      .transaction-card-info {
        margin-top: 12px;
      }

      .transation-amount {
        white-space: nowrap;
      }

      .view-all {
          width:100%;
          margin-top:24px;
          padding:16px 0px 16px 0px;
          background-color: #EDFFF5;
          border: 1px solid #DDFFEC;
          text-align: center;
      }
    }
  }
}
</style>
