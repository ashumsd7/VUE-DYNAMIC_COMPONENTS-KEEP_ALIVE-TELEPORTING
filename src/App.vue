<template>
  <div>
    <!-- <the-header></the-header> -->
    <!-- <badge-list></badge-list> -->
    <TheHeader/>
  <button @click="switchComponent('active-goals')">Active Goals</button> 
  <button @click="switchComponent('manage-goals')"> Manage Goals</button>
    <!-- <active-goals></active-goals>
    <manage-goals></manage-goals> -->
    <!-- now this will be manged by dynamic component -->
    <keep-alive>
      <component  :is="selectedComponent"></component>
    </keep-alive>
    <component  :is="selectedComponent"></component>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader'
import ActiveGoals from './components/ActiveGoals'
import ManageGoals from './components/ManageGoals'

export default {
  components:{
    TheHeader,
    ActiveGoals,
    ManageGoals
 
  },
  data() {
    return {
      activeUser: {
        name: 'Mahendra Singh Dhoni ',
        description: 'Cricketer :) ',
        role: 'admin',
      },

      selectedComponent: 'active-goals'
    };
  },
  methods: {
    switchComponent(cmp){
      this.selectedComponent= cmp;
    }
  },
  }

</script>

