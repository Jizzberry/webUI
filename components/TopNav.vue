<template>
<div class="center examplex">
    <vs-navbar text-white :color="active" fixed center-collapsed v-model="active">
        <template #left>
            <div class="navigation-tabs-holder">
                <vs-navbar-item :active="active == 'home'" id="home">
                    Home
                </vs-navbar-item>
                <vs-navbar-item :active="active == 'actors'" id="actors">
                    Actors
                </vs-navbar-item>
                <vs-navbar-item :active="active == 'categories'" id="categories">
                    Tags
                </vs-navbar-item>
            </div>
            <client-only>
                <Search></Search>
            </client-only>
        </template>
        <template #right>
            <div class="logo-holder">
                <Logo class="jizzberry-logo"></Logo>
                <TextLogo class="jizzberry-logo-text"></TextLogo>
            </div>
        </template>
    </vs-navbar>
</div>
</template>

<script>
import Logo from '@/components/Logo'
import TextLogo from '@/components/TextLogo'
import Search from '@/components/Search'
export default {
    components: {
        Logo,
        TextLogo,
        Search
    },
    data: () => ({
        active: '#ffbdf2'
    })
}
</script>

<style>
.logo-holder {
    display: flex;
    margin: 5px;
}

.jizzberry-logo {
    height: 60px;
    width: 60px;
}

.jizzberry-logo-text {
    height: 60px;
    width: 160px;
}
</style>
