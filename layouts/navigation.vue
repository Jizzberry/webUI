<!-- Only logo on scroll -->

<template>
<div>
    <TopNav class="topnav-fixed"></TopNav>
    <!-- <SecondNavBar class="second-nav"></SecondNavBar> -->
    <div class="nuxt-container">
        <nuxt />
    </div>
</div>
</template>

<script>
import TopNav from '@/components/TopNav'
import SecondNavBar from '@/components/SecondNavBar'
export default {
    components: {
        SecondNavBar,
        TopNav
    }
}
</script>

<style>
.nuxt-container {
    z-index: 1;
    margin-top: calc(70px + 10px);
}

.topnav-fixed {
    z-index: 3;
}

.second-nav {
    z-index: 2;
    display: flex;
    position: relative;
    margin-top: 70px;
}
</style>
