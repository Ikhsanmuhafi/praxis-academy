<template>
  <v-container class="mobile">
    <v-list-item-icon>
      <v-icon>mdi-cellphone</v-icon>
    <h2>Mobile</h2>
    </v-list-item-icon>
    <v-card class="con-items" v-for="user in users" :key="user.name">
      <v-list-item-icon>
        <v-icon>mdi-account-circle</v-icon>
        <v-card-title>{{user.name}} </v-card-title>
      </v-list-item-icon>
      <v-list-item-icon>
        <v-icon>mdi-home</v-icon>
       <v-card-title>{{user.address}} </v-card-title>
      </v-list-item-icon>
      <v-list-item-icon>
        <v-icon>mdi-cellphone-basic</v-icon>
        <v-card-title>{{user.hendpone}} </v-card-title>
      </v-list-item-icon>
    </v-card>
  </v-container>
</template>

<script>
export default {
  computed: {
    users() {
      return this.$store.state.user.filter((user) => {
        if (user.isApproved === false){
          user.status = 'Pending'
        }else{
          user.status = 'Approved'
        }
        return user.program === 'Mobile'
      })
    }
  }
}
</script>
<style>
.mobile{
  text-align: justify;
  max-width: 1500px;
}
</style>