<template>
<div class="center examplex">
    <vs-navbar text-white :color="active" hideScroll center-collapsed v-model="active">
        <vs-navbar-item :active="active == 'home'" id="home">
            Home
        </vs-navbar-item>
        <vs-navbar-item :active="active == 'actors'" id="actors">
            Actors
        </vs-navbar-item>
        <vs-navbar-item :active="active == 'categories'" id="categories">
            Tags
        </vs-navbar-item>
    </vs-navbar>
</div>
</template>

<script>
export default {
    data: () => ({
        active: '#ffbdf2'
    })
}
</script>

<style>
</style>
