<template>
    <div class="select_kind">
        <select v-model="selected" @change="$emit('change_kind',selected)" name="kind" id="kind_select">
          <option value="Rock">
            Rock
          </option>
          <option value="Pop">
              Pop
          </option>
          <option value="Jazz">
              Jazz
          </option>
          <option value="Metal">
              Metal
          </option>
        </select>
    </div>
</template>

<script>
export default {
    data(){
        return{
            selected:""
        }
    },
    methods:{
        
    }
 }
</script>

<style lang="scss">
    
</style>