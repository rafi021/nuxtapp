<template>
<div class="">
  <h1>Helllo User Id: {{ $route.params.id }}</h1>
</div>
</template>

<script>
export default{
  validate({params}){
    return /^\d+$/.test(params.id)
  }
}
</script>
