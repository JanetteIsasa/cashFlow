<template>
    <main>
        <p>{{labelVisual}}</p>
        <h1>{{amountCurrency}}</h1>
         <div class="graphic">
            <slot name="graphic"></slot>
        </div>
        <div class="action">
            <slot name="action"></slot>
        </div>
    </main>
</template>

<script>
const currencyFormatter = new Intl.NumberFormat("es-PY", {
  style: "currency",
  currency: "PYG",
});

export default{
    props: {
        totalLabel: {
            type: String,
        },
        label: {
            type: String,
            default: null,
        },
        totalAmount: {
            type: Number,
        },
        amount: {
            type: Number,
            default: null,
        },
    },
    computed:{
        labelVisual() {
            return this.label !== null ? this.label : this.totalLabel; 
        },
        //retorna el amount si no es null o sino el totalAmount
        //dependiendo de que seleccione el cliente
        amountVisual(){
            return this.amount !== null ? this.amount : this.totalAmount;
        },
        amountCurrency() {
            return currencyFormatter.format(this.amountVisual);
        }
    },
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}
h1,
p {
  margin: 0;
  text-align: center;
  color: white;
}
h1 {
  margin-top: 14px;
  color: var(--brand-celeste-claro2);
}
p{
    font-size: 1.1rem;
    padding-top: 0.5rem;
    
}
.graphic {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 24px;
  box-sizing: border-box;
}

@media screen and (min-width: 600px) {
    p{
        font-size: 1.5rem;
    }
  h1{
    font-size: 3.5rem;
  }
}
</style>