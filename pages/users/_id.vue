<template>
<div class="">
  <h1>Helllo User Id: {{ $route.params.id }}</h1>
</div>
</template>

<script>
export default{
  validate(context){
    return /^\d+$/.test(context.params.id)
  }
}
</script>
