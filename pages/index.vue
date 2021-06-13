<template>
  <div>
    <!-- STRAT NAVBAR -->
    <nav
      class="navbar navbar-expand-lg fixed-top navbar-white navbar-custom sticky sticky-dark"
      id="navbar"
    >
      <div class="container">
        <!-- LOGO -->
        <a class="navbar-brand logo text-uppercase" href="/">
          <img src="/logo.png" width="40px" />
        </a>

        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarCollapse"
          aria-controls="navbarCollapse"
          aria-expanded="false"
          aria-label="Toggle navigation"
          @click="toggleMenu()"
        >
          <i class="mdi mdi-menu"></i>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul
            class="navbar-nav navbar-center"
            id="mySidenav"
            v-scroll-spy-active="{ class: 'active' }"
          ></ul>
          <div class="nav-button ml-auto">
            <ul
              class="nav navbar-nav navbar-right"
              v-scroll-spy-active="{ class: 'active' }"
            >
              <li class="nav-item">
                <a
                  v-scroll-to="{ el: '#home' }"
                  class="nav-link"
                  data-scroll-spy-id="home"
                  href="javascript: void(0);"
                  >НҮҮР</a
                >
              </li>
              <li class="nav-item">
                <a
                  v-scroll-to="{ el: '#about', offset: -5 }"
                  class="nav-link"
                  data-scroll-spy-id="about"
                  href="javascript: void(0);"
                  >БИДНИЙ ТУХАЙ</a
                >
              </li>
              <li class="nav-item">
                <a
                  v-scroll-to="{ el: '#product', offset: -5 }"
                  class="nav-link"
                  data-scroll-spy-id="product"
                  href="javascript: void(0);"
                  >БҮТЭЭГДЭХҮҮН</a
                >
              </li>
              <li class="nav-item">
                <a
                  v-scroll-to="{ el: '#partner', offset: -100 }"
                  class="nav-link"
                  data-scroll-spy-id="partner"
                  href="javascript: void(0);"
                  >ХАМТРАГЧ БАЙГУУЛЛАГА</a
                >
              </li>
              <li class="nav-item">
                <a
                  v-scroll-to="{ el: '#contact', offset: -5 }"
                  class="nav-link"
                  data-scroll-spy-id="contact"
                  href="javascript: void(0);"
                  >ХОЛБОО БАРИХ</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
    <!-- END NAVBAR -->
    <div v-scroll-spy>
      <!--START HOME-->
      <section
        class="section bg-home home-half"
        id="home"
        style="background-size: cover;background-position: center;"
        :style="{
          background: 'url(/bg.jpg)'
        }"
      >
        <div class="bg-overlay"></div>
        <div class="container">
          <div class="row">
            <div class="col-lg-8 offset-lg-2 text-white text-center">
              <h1 class="home-title">Гэгээн хутагт</h1>
              <p class="padding-t-15 home-desc mx-auto">
                Эмнэлэгийн хэрэгсэл худалдаа
              </p>
            </div>
          </div>
        </div>
      </section>
      <!--END HOME-->

      <Features />
      <!-- <Services /> -->
      <About />
      <section class="section-sm bg-light" id="partner">
        <div class="container">
          <div class="about-title mx-auto text-center">
            <h2 class="section-title">
              ХАМТРАГЧ БАЙГУУЛЛАГА
            </h2>
          </div>
          <div class="row">
            <div
              class="col-md-2 my-3"
              v-for="(p, p_index) in partners"
              :key="p_index"
            >
              <div
                class="client-images my-3 my-md-0 boxshadow"
                style="display: flex; align-items: center; justofy-content: center; height: 100%"
              >
                <img
                  :src="`/partners/${p}`"
                  alt="logo-img"
                  class="mx-auto img-fluid d-block"
                />
              </div>
            </div>
          </div>
        </div>
      </section>
      <Contact />
      <Footer />
    </div>
  </div>
</template>
<script>
import Features from "@/components/features";
import Services from "@/components/services";
import About from "@/components/about";
import Pricing from "@/components/pricing";
import Testimonial from "@/components/testimonial";
import GetStarted from "@/components/getstarted";
import Blog from "@/components/blog";
import Contact from "@/components/contact";
import Footer from "@/components/footer";
export default {
  head() {
    return {
      title: "Гэгээн хутагт ХХК эмнэлэгийн хэрэгсэл худалдаа"
    };
  },
  data() {
    return {
      partners: [
        "1.jpg",
        "2.png",
        "3.png",
        "4.jpg",
        "5.jpg",
        "6.png",
        "7.png",
        "8.jpg",
        "9.jpg",
        "10.jpg",
        "11.jpg",
        "12.png",
        "13.jpg",
        "14.jpg",
        "15.png",
        "16.png",
        "17.jpg",
        "18.jpg",
        "19.jpg",
        "20.png",
        "21.jpg",
        "22.jpg",
        "23.jpg",
        "24.jpg"
      ]
    };
  },
  components: {
    Features,
    Services,
    About,
    Pricing,
    Testimonial,
    GetStarted,
    Blog,
    Contact,
    Footer
  },
  methods: {
    toggleMenu() {
      document.getElementById("navbarCollapse").classList.toggle("show");
    }
  }
};
</script>
<style scoped>
::v-deep .modal-content {
  background-color: #000000;
  color: white;
  background: none;
  border: none;
}
::v-deep .modal-header {
  border: none;
}
::v-deep .modal-backdrop {
  opacity: 0.5;
}
</style>
