<template>
    <footer class="pt-5 pb-5 border-top bg-dark text-white-50 links-white" style="border-color: #3d3d3d !important;">
        <div class="container">
            
            <div class="row mb-5">
                <div class="col-md mb-3">
                    
                    <ul class="list-unstyled text-center text-md-left">        
                        <li class="mb-3" v-for="item in menu">
                            <NuxtLink :to="item.name === 'index' ? '/' : item.name">{{ item.short_name }}</NuxtLink>
                        </li>
                    </ul>
                </div>
                
                <div class="col text-center text-md-right">
                    <p><img src="https://sales-team.matrix.squiz.cloud/__data/assets/image/0018/21735/squiz-logo-white.png" alt="Logo" width="130" height="58"></p>
                    <p>Gilmore is a multipurpose mini-site template for Squiz Matrix that lets you quickly and easily get started with a new web project.</p>
                    
                    <ul class="list-inline pt-3">
                        <li class="list-inline-item ml-2">
                            <a href="https://www.youtube.com/user/SquizGlobal" target="_blank" class="btn btn-light text-dark fa-center"><i class="fab fa-youtube"></i><span class="sr-only">Youtube</span></a>
                        </li>
                        <li class="list-inline-item ml-2">
                            <a href="https://www.linkedin.com/company/squiz" target="_blank" class="btn btn-light text-dark fa-center"><i class="fab fa-linkedin-in"></i><span class="sr-only">LinkedIn</span></a>
                        </li>
                        <li class="list-inline-item ml-2">
                            <a href="https://www.instagram.com/unsplash/" target="_blank" class="btn btn-light text-dark fa-center"><i class="fab fa-instagram"></i><span class="sr-only">Instagram</span></a>
                        </li>
                        <li class="list-inline-item ml-2">
                            <a href="https://www.facebook.com/SquizGlobal" target="_blank" class="btn btn-light text-dark fa-center"><i class="fab fa-facebook"></i><span class="sr-only">Facebook</span></a>
                        </li>
                        <li class="list-inline-item ml-2">
                            <a href="https://twitter.com/squizmatrix" target="_blank" class="btn btn-light text-dark fa-center"><i class="fab fa-twitter"></i><span class="sr-only">Twitter</span></a>
                        </li>
                    </ul>
                </div>    
            </div>
            
            <div class="row">
                <div class="col-md order-md-2">
                    <ul class="pb-3 list-inline mb-0 text-center text-md-right text-muted small">                
                        <li class="list-inline-item ml-3"><a href="https://sales-team.matrix.squiz.cloud/testing/gilmore/privacy">Privacy</a></li>                            
                        <li class="list-inline-item ml-3"><a href="https://sales-team.matrix.squiz.cloud/testing/gilmore/terms-and-conditions">Terms</a></li>            
                    </ul>
                </div><!--.col-->
                <div class="col-md text-center text-md-left order-md-1">
                    <p class="small">© <a href="https://www.squiz.net/" target="_blank">Squiz</a> 2021 &nbsp;|&nbsp; Website Powered by <a href="http://www.squiz.net/matrix" target="_blank">Squiz Matrix</a></p>
                </div><!--.col-->
            </div><!--.row-->
        </div>
    </footer>
</template>

<script>
    export default {
        components: {

        },
        data () {
            return {
                menu: []
            }
        },
        async fetch() {
            this.menu = await fetch(
                'https://nzdemos-web.squiz.cloud/jamstack/api/menu-listing/_nocache'
            )
            .then(res => res.json())
            .then(data => data)
        }
}
</script>

<style scoped>

</style>