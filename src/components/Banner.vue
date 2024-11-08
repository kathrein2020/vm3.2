<script setup>
//из banner app.vue
const {banner} =defineProps(["banner"])
const {
    title,
    overview,
    bacdrop_path,
    release_date,
    vote_average,
    original_language
} = banner

//console.log(banner)
</script>

<template>
    <!-- <h1 style="background-color: aliceblue;">HelloWorld111</h1> -->
     <h1>ff</h1>
    <p>{{ banner }}</p>
    <p>{{ banner.title}}</p>
</template>