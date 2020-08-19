<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <div class="form-group">
          <label for="example">Seu link foi gerado</label>
          <textarea
            class="form-control"
            id="url"
            rows="3"
            v-model="$route.params.link"
          ></textarea>
        </div>
      </div>
      <div class="col-12 d-flex justify-content-around">
        <button
          id="copiar"
          data-clipboard-target="#url"
          class="btn btn-success"
        >
          Copiar
        </button>
        <a target="_blank" :href="$route.params.link" class="btn btn-warning"
          >Testar</a
        >
        <router-link to="/" class="btn btn-danger">Gerar Novo Link</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import ClipboardJS from "clipboard";
new ClipboardJS("#copiar");

export default {};
</script>
