<template>
  <div class="conteinar">
    <h1>{{ message }}</h1>
    <p> {{ this.$route.params.id }}</p>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      message: 'id表示の確認'
    }
  },
  validate({ params }) {
    // 正規表現で数値のみしか表示しない
    return /^\d+$/.test(params.id)
  }
}
</script>>
