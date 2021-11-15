<template>
    <div>
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
        Image: String,
        title: String,
        artist:String,
        year:String
    }
}
</script>