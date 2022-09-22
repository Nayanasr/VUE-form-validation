<template>
   <navbar-comp />
  <form-comp @getFormDataFromLogin='getFormDataFromLogin'/>
  <user-table :userFormData="userFormData"/>
 
  <!-- vee-form is file is used when we are validating the form using VEEVALIDATE in
   chrome where that has the codes of form validating  -->
  <!-- <vee-form /> --> 
  
</template>

<script>

import NavbarComp from './components/NavbarComp.vue'
import FormComp from './components/FormComp.vue'
import UserTable from './components/UserTable.vue'
// import VeeForm from './components/VeeForm.vue'

export default {
  name: 'App',
  components: {
    
    NavbarComp,
    FormComp,
    UserTable,
    // VeeForm
   
  },
  data(){
    return{
      userFormData: []
    }

  },
  methods: {
    getFormDataFromLogin(formData){
      // console.log("formData in parent", formData);
      this.userFormData.push(formData)
      console.log("userFormData",this.userFormData);
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
