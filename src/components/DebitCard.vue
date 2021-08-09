<template>
   <div class="debit-card">
        <div class="flex flex-end">
          <img src="@/assets/remove_red_eye-24px.svg"  height="24" width="24"/>
          <label class="bold text-accent show-card-number">Show card number</label>
        </div>
        <div class="debit-card-card">
          <img src="@/assets/debit-card.png"  height="250" width="400"/>
        </div>
        <div class="debit-card-opearations flex">
          <div class="flex flex-column" v-for="item in items" :key="item.label">
              <img :src="item.icon" height="32" width="32" :alt="item.iconName">
              <label class="text-primary">{{item.label}}</label>
          </div>
        </div>
      </div>
</template>

<script>
    export default {
        name:"DebitCard",
    setup(){
        let items = [
            {'label':'Freeze Card','icon':require('@/assets/Freeze card.svg'),'iconName':'Freeze Card'},
            {'label':'Set limit','icon':require('@/assets/Set spend limit.svg'),'iconName':'Set spend limit'},
            {'label':'Add GPay','icon':require('@/assets/GPay.svg'),'iconName':'Add to GPay'},
            {'label':'Replace card','icon':require('@/assets/Replace card.svg'),'iconName':'Replace card'},
            {'label':'Cancel card','icon':require('@/assets/Deactivate card.svg'),'iconName':'Cancel card'},
        ];
        return {items};
    },
    }
</script>

<style lang="scss" scoped>

@import "@/styles/_variables.scss";

.debit-card {
      width:100%;
      margin-right:46px;
      .flex {
          :first-child{
              
          }
      }
      .show-card-number{
          margin-left: 8px;
      }

      .debit-card-card {
          border-radius: $border-radius-sm;
      }

      .debit-card-opearations {
          border-radius: 16px;
          background-color: $bg-primary-soft;
          margin-top: 56px;
          padding:20px 30px 20px 30px;
          text-align:center;
          align-items: baseline;

          .flex {
              
              align-items:center;
              margin:0px 8px 0px 8px;

              label{
                  padding-top: 8px;
              }
          }
      }
    }

</style>