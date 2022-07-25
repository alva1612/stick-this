<template>
  <div class="sticker-container">
    <div class="sticker-content">
            <h2>{{titulo}}</h2>
            <p>{{descripcion}}</p>
    </div>
    <div class="sticker-tools">
        
    </div>
  </div>
</template>

<script>
export default {
  props: {
    titulo: String,
    descripcion: String,
  }
}
</script>

<style>
.sticker-content {
  background-color: antiquewhite;
  border-radius: 30px;
  min-height: 200px; 
}
</style>