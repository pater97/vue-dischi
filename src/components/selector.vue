<template>
    <div class="select_kind">
        <h1>FILTRA IN BASE AL GENERE</h1>
        <select v-model="selected" @change="$emit('filteredKind',selected)" name="kind" id="kind_select">
            <option value="all">
                all
            </option>
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
    }
 }
</script>

<style lang="scss">
.select_kind{
    display: flex;
    flex-direction: column;
    align-items: center;
    h1{
        color: #1ed760;
    }
    #kind_select{
        background-color: transparent;
        color:#1ed760 ;
        border: 2px solid #1ed760;
        padding:.5rem 1rem;
        border-radius: 10px;
        font-size: 1.5rem;
        margin: 2rem 0;
        &:hover{box-shadow: 1px 1px 15px 1px #1ed760;}
    }
}
</style>