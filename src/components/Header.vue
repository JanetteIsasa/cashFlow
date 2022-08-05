<template>
  <header>
    <img @click="reload" src="@/assets/cashflow-icon.svg" alt="Logo" />
    <h1><span>Cash</span>Flow</h1>
    <span></span>
  </header>
</template>

<script>
export default {
  methods: {
    reload() {
      location.reload();
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
}

img,
span {
  width: 48px;
}

h1 {
  font-size: 1.4rem;
  color: var(--brand-naranja);
  text-shadow: 2px 2px 4px #000000;
}
h1 span{
  color: var(--brand-celeste-claro2);
}


@media screen and (min-width: 600px) {

  img,
  span {
    width: 4.5rem;
  }

  h1 {
    font-size: 2.5rem;

  }
}
</style>