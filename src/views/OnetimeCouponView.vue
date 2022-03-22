<script setup lang="ts">
import { ref } from "vue";
let isUsed = ref(false);
function useCoupon() {
  isUsed.value = true;
}
</script>

<template>
  <main>
    <div class="container">
      <div class="image-parent">
        <img src="@/assets/nizami-coffee-2.jpg" alt="quixote" />
      </div>
      <div class="card coupon-detail-card">
        <div class="card-body">
          <h5 class="card-title">
            【1個無料】みらいに珈琲で販売している豆200g いずれか1点
          </h5>
          <p class="coupon-detail-p-statement">
            <span class="text-primary">有効期限</span> 2022/3/28(月)
          </p>
          <p class="coupon-detail-p-statement">みらいに株式会社</p>
          <p class="coupon-detail-p-statement">石川県珠洲市熊谷町8の部3番地</p>
          <p class="coupon-detail-p-statement">000-0000-0000</p>
          <div class="coupon-detail-caution">
            <p class="coupon-detail-p-statement text-secondary">
              対象商品が売り場にあるか事前にご確認ください。 <br />
              他のクーポン券などを同一の商品で併用することはできません。 <br />
              同一会計で同じクーポン（同一期間、同一値引額）を2枚以上ご利用いただくことはできません。<br />
              ※画像は一例・イメージです。<br />
              ※偽造・転売などの不正行為があった場合、本クーポンは無効となります。
            </p>
          </div>
          <hr />
          <div class="coupon-detail-barcode">
            <div class="d-grid gap-2 col-6 mx-auto">
              <button
                class="btn btn-primary"
                type="button"
                v-if="!isUsed"
                @click="useCoupon"
              >
                使用する
              </button>
              <button class="btn btn-secondary" type="button" v-if="isUsed">
                使用済みです
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.image-parent {
  text-align: center;
}
.coupon-detail-budge-spacer {
  margin-left: 8px;
}
.coupon-detail-card {
  margin-top: 16px;
}
.coupon-detail-p-statement {
  margin-bottom: 0px;
}
.coupon-detail-caution {
  padding-top: 24px;
}
.coupon-detail-barcode {
  text-align: center;
}
h5 {
  font-size: 14px;
}
p {
  font-size: 12px;
}
</style>
