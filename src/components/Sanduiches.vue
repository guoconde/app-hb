<template>
  <div>
      <div>
          <div>Burger</div>
          <input type="text" v-model="burger" >
          <button @click="burger++">Acrescentar</button>
          <button @click="burger--">Remover</button>
      </div>
      <div>
          <div>Cheddar</div>
          <input type="text" v-model="cheddar" >
          <button @click="cheddar++">Acrescentar</button>
          <button @click="cheddar--">Remover</button>
      </div>
      <div>
          <div>Pedido</div>
          <span>{{ pedidoFinal }}</span>
          <button @click="getPedidoFinal">Ok</button>
          <button @click="enviarPedido">Enviar Pedido</button>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        getPedidoFinal() {
            this.valorFinal()
            if(this.pedidoFinal == '') {
                if(this.burger > 0) {
                    this.pedidoFinal += `${this.burger} Burger `
                }
                if(this.cheddar > 0) {
                    this.pedidoFinal += `${this.cheddar} Cheddar`
                }
            } else {
                this.pedidoFinal = ''
                if(this.burger > 0) {
                    this.pedidoFinal += `${this.burger} Burger `
                }
                if(this.cheddar > 0) {
                    this.pedidoFinal += `${this.cheddar} Cheddar`
                }
            }
        },
        enviarPedido() {
            const teste = this.pedidoFinal
            const teste1 = teste.replaceAll(' ', '%20')
            console.log(teste1)
        },
        valorFinal() {
            if(this.pedidoFinal == '') {
                if(this.burger > 0) {
                    this.pedidoFinal += this.burger * this.burgerValor
                }
                if(this.cheddar > 0) {
                    this.pedidoFinal += this.cheddar * this.cheddarValor
                }
            } else {
                this.pedidoFinal = ''
                if(this.burger > 0) {
                    this.pedidoFinal += this.burger * this.burgerValor
                }
                if(this.cheddar > 0) {
                    this.pedidoFinal += this.cheddar * this.cheddarValor
                }
            }
        }

    
    },
    data() {
        return {
            burger: '',
            cheddar: '',
            pedidoFinal: '',
            burgerValor: 20,
            cheddarValor: 20,
        }
    }
}
</script>

<style>

</style>
