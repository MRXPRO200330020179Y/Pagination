<template>
    <section class="news">
        <div class="news__top">
            <div class="news__list" v-for="(newmax,index) in newsmax" :key="index">
                <img :src="newmax.img" :alt="newmax.img">
            </div>
        </div>
    </section>
</template>


<script>
export default {
    props:['newsmax']
}
</script>