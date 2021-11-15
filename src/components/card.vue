<template>
    <div class="card">
        <img :src="image" alt="">
        <h2>
            {{title}}
        </h2>
        <h5>
            {{artist}}
        </h5>
        <h6>
            {{year}}
        </h6>
    </div>
</template>

<script>
export default {
    props:{
        image: String,
        title: String,
        artist:String,
        year:String
    }
}
</script>

<style lang="scss">
.card{
    width: calc((100%/12)*2);
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    img{
        width: 6rem;
    }
    h2{
        font-size: 1rem;
        width: 5rem;
    }
}
</style>