<template>
  <header class="header-area header-style-two header--fixed color-black">
    <div class="header-wrapper">
      <div class="header-left d-flex align-items-center">
        <div class="logo">
          <router-link to="/">
            <img
              src="../assets/images/logo/logo-symbol-dark.png"
              alt="Digital Agency"
            />
          </router-link>
        </div>
        <nav class="mainmenunav d-lg-block ml--50">
          <ul class="mainmenu">
            <li class="has-droupdown">
              <router-link to="/">Home</router-link>
            </li>
            <li class="has-droupdown">
              <router-link to="/service">Service</router-link>
            </li>
            <li><router-link to="/about">About</router-link></li>

            <li class="has-droupdown">
              <router-link to="/pages">Pages</router-link>
            </li>
            <li class="has-droupdown">
              <router-link to="/blocks">Blocks</router-link>
            </li>
            <li><router-link to="/contact">Contact</router-link></li>
          </ul>
        </nav>
      </div>
      <div class="header-right">
        <div class="social-share-inner">
          <ul
            class="social-share social-style--2 color-black d-flex justify-content-start liststyle"
          >
            <!-- {SocialShare.map((val , i) => (
                                    <li key={i}><a href={`${val.link}`}>{val.Social}</a></li>
                                ))} -->
            <li></li>
          </ul>
        </div>
        <div class="header-btn">
          <a
            class="rn-btn"
            href="https://themeforest.net/checkout/from_item/25457315?license=regular"
          >
            <span>buy now</span>
          </a>
        </div>
        <!-- {/* Start Humberger Menu */} -->
        <!-- <div class="humberger-menu d-block d-lg-none pl--20">
          <span onClick="{this.menuTrigger}" class="menutrigger text-white"
            ><FiMenu
          /></span>
        </div> -->
        <!-- {/* End Humberger Menu */} -->
        <!-- <div class="close-menu d-block d-lg-none">
          <span onClick="{this.CLoseMenuTrigger}" class="closeTrigger"
            ><FiX
          /></span>
        </div> -->
      </div>
    </div>
  </header>
</template>
<script>
import $ from "jquery";
export default {
  name: "Header",
  data() {
    return {
      currentScrollTop: 0,
    };
  },
  methods: {
    scroll() {
      window.onscroll = () =>
        (this.currentScrollTop = document.documentElement.scrollTop);
    },
  },
  mounted() {
    this.scroll();
  },
  watch: {
    currentScrollTop(newVal) {
      this.currentScrollTop > 110
        ? $(".header--fixed").addClass("sticky")
        : $(".header--fixed").removeClass("sticky");
      this.currentScrollTop = newVal;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~@/assets/scss/default/_variables.scss";

.header-wrapper .mainmenunav ul.mainmenu > li a {
  position: relative;
  &::after {
    position: absolute;
    content: "";
    left: 0;
    width: 0;
    height: 3px;
    background: $theme-color;
    transition: 0.3s;
    bottom: 0;
  }
  &.router-link-exact-active {
    color: $theme-color;;
    &::after {
      width: 100% !important;
    }
  }
}
</style>
