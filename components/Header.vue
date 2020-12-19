<template>
  <div>
    <p class="header-title">{{ headerText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headerText: 'Navita',
    }
  },
}
</script>

<style>
.header-title {
  color: #1cc88a;
  font-size: 1.1em;
  margin-left: 35px;
  font-weight: bold;
}
/* Texto: #5A5C69
Fundo: #F7F8FB
Cabeçalho e rodapé: #FFFFFF
Botão: #4E73DF
Botão ativo: #1CC88A
Cabeçalho do card: #F8F9FC
Sombra do card e cabeçalho: rgba(58, 59, 69, .15)
Bordas da tabela: #E3E6F0 */
</style>
