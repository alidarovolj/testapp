<template>
    <div class="container mx-auto">
        <img class="w-full" :src="$route.params.item.urls.regular" alt="">
    </div>
</template>

<script>
export default {
    name: "SingleView"
}
</script>