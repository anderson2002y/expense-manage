<script setup>
  import { ref } from 'vue';

  const presupuesto = ref(0);

  const definirPresupuesto = () => {
    if(presupuesto.value <= 0 ) {
      alert('presupuesto no valido');
    }
  }
</script>

<template>
  <form 
    class="presupuesto"
    @submit.prevent="definirPresupuesto"
  >

    <div class="campo">
      <label for="nuevo-presupuesto">Definir presupuesto</label>
      <input 
        type="number"
        id="nuevo-presupuesto"
        class="nuevo-presupuesto"
        placeholder="Agrega tu presupuesto"
        min="0"
        v-model.number="presupuesto"
      >
    </div>

    <input 
      type="submit"
      >

  </form>
</template>

<style scoped>

  .presupuesto {
    width: 100%;
  }

  .campo {
    display: grid;
    gap: 2rem;
  }

  .presupuesto label {
    font-size: 2.2rem;
    text-align: center;
    color: var(--azul);

  }

  .presupuesto input[type="number"] {
    background-color: var(--gris-claro);
    border-radius: 1rem;
    padding: 1rem;
    border: none;
    font-size: 2.2rem;
    text-align: center;
  }

  .presupuesto input[type="submit"] {
    background-color: var(--azul);
    border-radius: 1rem;
    border: none;
    padding: 1rem;
    margin-top: 2rem;
    font-size: 2rem;
    text-align: center;
    color: var(--blanco);
    font-weight: 900;
    width: 100%;

    transition: background-color 300ms ease;
  }

  .presupuesto input[type="submit"]:hover {
    background-color: var(--azul-oscuro);
    cursor: pointer;
  }

</style>