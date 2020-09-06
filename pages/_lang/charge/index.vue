<template>
  <div class="container">
    <div class="m-table">
      <!-- <div class="m-t-head">
        <div class="m-table-head">ID</div>
        <div class="m-table-head">Business ID</div>
        <div class="m-table-head">Status</div>
        <div class="m-table-head">ID</div>
      </div>
      <div class="m-t-body">
        <div class="m-t-b-rw" v-for="(order, idx) in orders" :key="idx">
          <div class="m-table-boby">{{ order.id }}</div>
          <div class="m-table-boby">{{ order.business_id}}</div>
          <div class="m-table-boby">{{ order.order_status_id }}</div>
          <div class="m-table-boby">ID</div>
        </div>
      </div>-->
    </div>

    <div></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      orders: [],
    };
  },
  mounted() {
    this.$axios.get("charge").then((res) => {
      console.log(res.data);
      this.orders = res.data;
    });
  },
};
</script>

<style lang="scss" scoped>
.m-table {
  display: grid;

  .m-t-head {
    display: grid;
    grid-template-columns: auto auto auto auto;
  }

  .m-t-body {
    .m-t-b-rw {
      display: grid;
      grid-template-columns: auto auto auto auto;
    }
  }
}
</style>