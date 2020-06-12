<template>
  <div class="mobileComponents">
    <threeLevelLinkage
      @Cevent="fn"
      :showVal="isThreeLevelLinkage"
    ></threeLevelLinkage>
    <button @click="fn1">省市区</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import threeLevelLinkage from "../components/tool/threeLevelLinkage/threeLevelLinkage.vue";
interface City {
  province: string;
  city: string;
  area: string;
}
@Component({
  components: {
    threeLevelLinkage
  }
})
export default class MobileComponents extends Vue {
  // 是否显示省市区
  isThreeLevelLinkage: boolean | City = false;
  city: City = {
    province: "安徽省",
    city: "池州市",
    area: ""
  };

  fn(e: string | City) {
    if (e === "取消") {
      this.isThreeLevelLinkage = false;
    } else {
      this.city = e as City;
      this.isThreeLevelLinkage = false;
    }
  }

  fn1() {
    this.isThreeLevelLinkage = this.city;
  }
}
</script>
<style lang="less" scoped></style>
