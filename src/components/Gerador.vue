<template>
  <div class="col-12 py-5">
    <div class="form-group">
      <label for="">Número</label>
      <input type="text" v-model="numero" class="form-control">
    </div>
    <div class="form-group">
      <label for="">Mensagem</label>
      <input type="text" v-model="mensagem" class="form-control">
    </div>
    <button @click="geraLink()" class="btn btn-primary btn-lg btn-block">Gerar Link</button>
  {{url}}
  </div>
</template>

<script>
export default {
  name: "Gerador",
  data: function() {
    return {
      numero: "",
      mensagem: "",
      url: "",
    };
  },
  methods: {
    geraLink: function() {
      let n = this.numero.replace(/[^0-9]/g, '');
      let m = encodeURI(this.mensagem)
      this.url = `https://wa.me/send?phone=${n}&text=${m}`;
      this.$router.push({ name: 'Resultado', params: {
        link: this.url
      } });
    }
  }
};
</script>
