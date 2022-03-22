<script setup lang="ts">
import { ref } from "vue";
const couponList = ref([
  {
    useAlways: 1,
    isNew: 1,
    title: "【1個無料】みらいに珈琲で販売している豆200g いずれか1点",
    deadline: "2022/3/28(月)",
    corporationName: "みらいに株式会社",
    zipcode: "927-1212",
    address: "石川県珠洲市熊谷町8の部3番地",
    tel: "000-0000-0000",
  },
  {
    useAlways: 1,
    isNew: 0,
    title: "【1個無料】みらいに珈琲で販売している豆200g いずれか1点",
    deadline: "2022/3/28(月)",
    corporationName: "みらいに株式会社",
    zipcode: "927-1212",
    address: "石川県珠洲市熊谷町8の部3番地",
    tel: "000-0000-0000",
  },
  {
    useAlways: 0,
    isNew: 0,
    title: "【1個無料】みらいに珈琲で販売している豆200g いずれか1点",
    deadline: "2022/3/28(月)",
    corporationName: "みらいに株式会社",
    zipcode: "927-1212",
    address: "石川県珠洲市熊谷町8の部3番地",
    tel: "000-0000-0000",
  },
]);
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col-12">
          <ul class="list-group">
            <a
              v-for="(coupon, index) in couponList"
              :key="index"
              class="list-group-item list-group-item-action d-flex align-items-center"
              href="/coupondetail"
            >
              <div class="image-parent">
                <img
                  src="@/assets/nizami-coffee-2.jpg"
                  alt="quixote"
                  width="75px"
                  height="100px"
                />
              </div>
              <div class="coupons-content-area">
                <h6>
                  <span class="badge bg-warning" v-if="coupon.useAlways === 0">
                    1回限定
                  </span>
                  <span class="badge bg-info" v-if="coupon.useAlways === 1">
                    何度でも使える
                  </span>
                  <span
                    class="badge bg-danger rounded-pill coupons-budge-spacer"
                    v-if="coupon.isNew === 1"
                  >
                    NEW
                  </span>
                </h6>
                <h5 class="font-midium">
                  {{ coupon.title }}
                </h5>
                <p class="coupons-p-statement">
                  <span class="text-primary">有効期限</span>
                  {{ coupon.deadline }}
                </p>
                <p class="coupons-p-statement">{{ coupon.corporationName }}</p>
                <p class="coupons-p-statement">〒{{ coupon.zipcode }}</p>
                <p class="coupons-p-statement">{{ coupon.address }}</p>
                <p class="coupons-p-statement">{{ coupon.tel }}</p>
              </div>
            </a>
          </ul>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.image-parent {
  max-width: 100px;
}
.coupons-budge-spacer {
  margin-left: 8px;
}
.coupons-content-area {
  padding-left: 32px;
}
.coupons-p-statement {
  margin-bottom: 0px;
}
h5 {
  font-size: 14px;
}
p {
  font-size: 12px;
}
</style>
