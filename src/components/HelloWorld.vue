<template>
  <v-container class="fill-height">
    <v-responsive class="d-flex align-center text-center fill-height">
        <h1 class="text-9xl">
          {{ msg }}
        </h1>
    </v-responsive>
  </v-container>
</template>

<script >
  export default {
    data(){
      return{
        msg:"Aloha!"
      }
    }}
  
</script>
