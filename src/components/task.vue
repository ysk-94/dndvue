<template>
  <li class="list">
    <slot></slot>
  </li>
</template>

<script>

</script>

<style>
.list {
  display: flex;
  padding: 8px 0;
  border: 1px solid #333;
}

.list div {
  margin: 0 8px;
}
</style>