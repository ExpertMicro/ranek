<template>
  <form>
    <input name="busca" id="busca" type="text" v-model="busca" placeholder="Buscar...">
    <input type="submit" id="lupa" value="Buscar" @click.prevent="buscarProdutos">
  </form>
</template>


<script>
export default {
  data() {
    return {
      busca: ""
    }
  },
  methods: {
    buscarProdutos() {
      this.$router.push({ query: { q: this.busca } })
    }
  }
}
</script>


<style scoped>
form {
  position: relative;
  max-width: 600px;
  margin: 30px auto 60px auto;
  padding: 0 10px;
}

#busca {
  width: 100%;
  box-shadow: 0 4px 8px rgba(30, 60, 90, 0.1);
  padding: 20px;
  border: none;
}

#busca:focus,
#busca:hover {
  transform: scale(1.1);
}

#lupa {
  width: 62px;
  height: 62px;
  background: url(../assets/search.svg) no-repeat center center;
  text-indent: -150px;
  border: none;
  cursor: pointer;
  position: absolute;
  box-shadow: none;
  top: 0;
  right: 0;
}
</style>