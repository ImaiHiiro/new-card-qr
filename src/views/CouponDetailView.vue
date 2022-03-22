<script>
import bwipjs from "bwip-js";
export default {
  data() {
    return {};
  },
  mounted() {
    let canvas = document.createElement("canvas");
    try {
      bwipjs.toCanvas(canvas, {
        bcid: "code128", // バーコード規格（必須）
        text: "0123456789", // バーコードに持たせたいテキストデータ（必須）
        scale: 3, // 生成画像の拡大率（任意）
        height: 10, // 生成画像の高さをインチで指定（任意）
        includetext: true, // バーコードの元のテキストデータを画像の下に表示するか（任意）
        textxalign: "center", // 生成画像におけるバーコードの位置を指定（任意）
      });
      document.getElementById("mycanvas").src = canvas.toDataURL();
    } catch (e) {
      console.error(e);
      return;
    }
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="image-parent">
        <img
          src="@/assets/nizami-coffee-2.jpg"
          alt="quixote"
          width="200px"
          height="200px"
        />
      </div>
      <div class="card coupon-detail-card">
        <div class="card-body">
          <h6>
            <span class="badge bg-info"> 何度でも使える </span>
            <span
              class="badge bg-danger rounded-pill coupon-detail-budge-spacer"
            >
              NEW
            </span>
          </h6>
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
            <img id="mycanvas" src="" alt="" />
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
