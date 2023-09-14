<template>
    <div id="main-menu" class="wsmainfull menu clearfix">
        <div class="wsmainwp clearfix">
            <!-- HEADER BLACK LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-black"><img src="/assets/images/logo-dark.png" alt="logo" /></NuxtLink>
            </div>
            <!-- HEADER WHITE LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-white"><img src="/assets/images/logo-white.png" alt="logo" /></NuxtLink>
            </div>
            <!-- MAIN MENU -->
            <nav class="wsmenu clearfix">
                <ul class="wsmenu-list nav-theme">
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/" class="h-link">Trang chủ</NuxtLink></li>
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/about" class="h-link">Giới thiệu</NuxtLink></li>
                    <!-- DROPDOWN SUB MENU -->
                    <li aria-haspopup="true" class="mg_link" :class="{ open: isOpen[0] }">
                        <span class="wsmenu-click 123" @click="toggle(0)"><i class="wsmenu-arrow"></i></span>
                        <NuxtLink to="#" class="h-link">Sản phẩm <span class="wsarrow"></span></NuxtLink>
                        <div class="wsmegamenu w-75 clearfix">
                            <div class="container">
                                <div class="row">
                                    <!-- MEGAMENU LINKS -->
                                    <ul class="col-md-12 col-lg-6 link-list">
                                        <li><NuxtLink to="/demo-1">Khách gửi hàng</NuxtLink></li> 
                                    </ul>
                                    <ul class="col-md-12 col-lg-6 link-list">
                                        <li><NuxtLink to="/demo-8">Khách doanh nghiệp</NuxtLink></li> 
                                    </ul>
                                     
                                </div>
                            </div>
                        </div>
                    </li>
                      
                    <!-- SIMPLE NAVIGATION LINK -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/pricing-1" class="h-link">Bảng giá</NuxtLink></li>
                    <!-- SIMPLE NAVIGATION LINK -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/pricing-1" class="h-link">Bưu cục</NuxtLink></li>
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/pricing-1" class="h-link">Tin tức</NuxtLink></li>

                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/faqs" class="h-link">FAQs</NuxtLink></li>
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/contacts" class="h-link">Liên hệ</NuxtLink></li>
                    
                    <!-- SIGN UP BUTTON -->
                    <li class="nl-simple" aria-haspopup="true">
                        <NuxtLink to="/signup-2" class="btn r-04 btn--theme hover--tra-white last-link">Sign up</NuxtLink>
                    </li>
                </ul>
            </nav>
            <!-- END MAIN MENU -->
        </div>
    </div>
</template>
<script>
import { reactive } from 'vue';
export default {
    setup() {
        const state = reactive({
        isOpen: [false, false]
        });
        const toggle = (index) => {
        state.isOpen[index] = !state.isOpen[index];
        };
        return {
        toggle,
        isOpen: state.isOpen
        };
    },
    mounted() {
        window.addEventListener("scroll", this.handleScroll);
    },
    destroyed() {
        window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll() {
            const menu = document.getElementById("main-menu");
            const header = document.getElementById("header");
            if (window.pageYOffset > 100) {
                menu.classList.add("scroll");
                header.classList.add("scroll");
            } else {
                menu.classList.remove("scroll");
                header.classList.remove("scroll");
            }
        }
    }
};
</script>
