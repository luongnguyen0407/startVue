<template>
  <table class="table">
    <thead>
      <tr>
        <th>STT</th>
        <th>Tên</th>
        <th>Giá</th>
        <th>Số lượng trong kho</th>
        <th>Số lượng</th>
        <th>Thành tiền</th>
        <th>Hành động</th>
      </tr>
    </thead>
    <tbody v-if="productCart">
      <tr v-for="(product, index) in productCart" :key="product.id">
        <td scope="row">{{ index++ }}</td>
        <td>{{ product.name }}</td>
        <td>{{ formatPrice(product.price) }}</td>
        <td>{{ product.quantityInStock }}</td>
        <td class="d-flex">
          <i class="fa fa-arrow-down btn btn-success"></i>
          <span class="mx-2">{{ product.amount }}</span>
          <i class="fa fa-arrow-up btn btn-success"></i>
        </td>
        <td>{{ formatPrice(+product.price * +product.amount) }}</td>
        <td>
          <button
            class="btn btn-danger d-block mx-auto"
            @click="handleDeleteProduct(product)"
          >
            <i class="fa fa-trash"></i>
          </button>
        </td>
      </tr>
      <tr>
        <td scope="row">Total</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>{{ formatPrice(sumMoney) }}d</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import formatPrice from "../FormatNumber.js";
import { inject, reactive, toRef } from "vue";
export default {
  inject: ["productCart", "delProduct"],
  data() {
    return {
      formatPrice,
      isOpen: false,
    };
  },
  setup() {
    const productCart = inject("productCart");
    const listProduct = reactive(productCart);
    return toRef(listProduct);
  },
  computed: {
    sumMoney() {
      return this.productCart.reduce((sum, product) => {
        return (sum += +product.price * +product.amount);
      }, 0);
    },
  },
  methods: {
    handleDeleteProduct(product) {
      // this.listProduct = this.listProduct.filter(
      //   (item) => item.id !== product.id
      // );
      // this.productCart = this.listProduct;
      this.delProduct(product);
    },
  },
};
</script>

<style></style>
