<template>
<div class="">
  <h1>Hello World</h1>

  <no-ssr>
    <v-select v-model="selected" placeholder="Select an Category" :options="['foo', 'bar']"></v-select>
  </no-ssr>
</div>
</template>

<script>
export default{
  name: 'IndexPage',
  layout: 'blog',
  data() {
    return {
      selected: ''
    }
  }
}
</script>
