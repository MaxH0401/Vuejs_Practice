<template>
<div class='product-item'>
    <h3>{{name}}</h3>{{price}}</div>
</template>

<script>
export default {
  name: "ProductItem",
  props:['name','price']
};
</script>

<style>
.product-item {
  width: calc(25% - 10px); 
    /* 25% 減 10px，是為了減margen造成的10px，如果沒減掉，那會被擠到下一行 */
  margin: 0 5px 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: 0 2px 5px #aaa;
  padding: 10px;
  background: #d33434;
  color: #f1f1f1;
}
</style>