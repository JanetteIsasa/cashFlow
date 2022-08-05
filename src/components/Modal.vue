<template>
  <div class="modal">
    <div class="modal-contenido">
    <div class="head">
      <p>Nuevo movimiento</p>
      <img @click="close" src="@/assets/close-icon.svg" alt="cerrar" />
    </div>
    <div class="body">
      <slot></slot>
    </div>
  </div>
  </div>
  
</template>

<script setup>
import { defineEmits } from "vue";
const emit = defineEmits(["close"]);
const close = () => emit("close");
</script>

<style scoped>
.modal-contenido {
  z-index: 2;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: var(--brand-celeste-claro2);
}
.head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 24px 24px;
  box-sizing: border-box;
  
}
p {
  margin: 0;
  font-size: 1.5rem;
  color: var(--brand-celeste);
  font-weight: bold;
}

@media screen and (min-width: 600px) {
   .modal-contenido{
    width:500px;
    padding: 10px 20px;
    padding-bottom: 30px;
    margin: 20% auto;
    height: max-content;
   }

  .modal{
  background-color: rgba(0,0,0,.8);
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;  
}
}
</style>