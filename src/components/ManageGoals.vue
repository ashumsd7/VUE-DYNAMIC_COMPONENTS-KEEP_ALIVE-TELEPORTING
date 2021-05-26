<template>
        <h2>Manage Goals</h2>
        <input ref="goal" type="text">
        <button @click="saveGoal">SetGoal</button>
        <teleport to="body">
        <ErrorPlateSlot v-if="showError">
            <h3>Please Enter something</h3>
            <button @click="hideErrrorSlot">OK</button>
        </ErrorPlateSlot>
        </teleport>

</template>

<script>
import ErrorPlateSlot   from './ErrorPlateSlot'
export default {
    components:{
        ErrorPlateSlot
    },
    data(){
        return{
            showError:false
        }
    },
    methods: {
        saveGoal(){
            const goal= this.$refs.goal.value;
            if(!goal){
                // alert('input must not empty'); 
                this.showError=true;
            }
        },
        hideErrrorSlot(){
            this.showError= !this.showError;
        }
    },
}
</script>