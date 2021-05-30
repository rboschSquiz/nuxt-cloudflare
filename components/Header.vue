<template>
    <header id="top" class="main-header bg-white border-bottom">
        <div class="navbar fixed-top shadow-sm bg-white navbar-expand-lg border-bottom">
            <div class="container" id="navbar-toggle">
                
                <!-- Logo -->
                <a class="navbar-brand" href="https://sales-team.matrix.squiz.cloud/testing/gilmore">
                    <img src="https://sales-team.matrix.squiz.cloud/__data/assets/image/0016/21733/squiz-logo.png" width="164" height="74" alt="Site header logo" title="Site header logo">
                    <span class="align-middle sr-only">Site Name</span>
                </a>
                
                <!-- Main nav toggle button -->
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#main-navbar" aria-controls="main-navbar" aria-expanded="false" aria-label="Toggle navigation">
                    <i class="fas fa-bars"></i>
                </button>
                
                <!-- Main Navigation -->
                <div class="collapse navbar-collapse flex-grow-0 ml-auto order-md-2 order-lg-1" id="main-navbar" data-parent="#navbar-toggle">
                    <ul class="navbar-nav ml-auto mr-2 pt-lg-0 pt-3" v-if="!loading">        
                        <li class="nav-item px-lg-3 mb-2 mb-lg-0" v-for="item in menu">
                            <NuxtLink :to="item.name === 'index' ? '/' : item.name">{{ item.short_name }}</NuxtLink>
                        </li>
                    </ul>
                </div><!--.collapse-->
            </div><!--.container-->
        </div><!--.navbar-->
    </header>
</template>

<script>
    export default {
        components: {

        },
        data () {
            return {
                menu: [],
                loading: true
            }
        },
        mounted: function () {
            this.getContent()
        },
        methods: {
            getContent: function () {
            // this.$axios.$get('https://nzdemos-web.squiz.cloud/jamstack/home?SQ_PAINT_LAYOUT_NAME=json&SQ_DESIGN_NAME=json', {})
                this.$axios.$get('https://nzdemos-web.squiz.cloud/jamstack/api/menu-listing/_nocache', {})
                    .then((data) => {
                        this.menu = data
                        this.loading = false
                    })
            }
        }
}
</script>

<style lang="scss">
    .main-header {
        margin-bottom: 100px;
    }
</style>