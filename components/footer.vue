<script>
/**
 * Footer component
 */
export default {
  name: "Footer"
};
</script>

<template>
  <div>
    <!--START FOOTER ALTER-->
    <div class="footer-alt">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="float-left pull-none">
              <p class="copy-rights text-muted mb-3 mb-sm-0">
                {{ new Date().getFullYear() }} © Гэгээн хутагт ХХК эмнэлэгийн
                хэрэгсэл худалдаа
              </p>
            </div>
            <div class="float-right pull-none">
              <ul class="list-inline social m-0">
                <li class="list-inline-item">
                  <a
                    target="_blank"
                    href="https://www.facebook.com/%D0%93%D1%8D%D0%B3%D1%8D%D1%8D%D0%BD-%D1%85%D1%83%D1%82%D0%B0%D0%B3%D1%82-%D0%A5%D0%A5%D0%9A-%D1%8D%D0%BC%D0%BD%D1%8D%D0%BB%D1%8D%D0%B3%D0%B8%D0%B9%D0%BD-%D1%85%D1%8D%D1%80%D1%8D%D0%B3%D1%81%D1%8D%D0%BB-%D1%85%D1%83%D0%B4%D0%B0%D0%BB%D0%B4%D0%B0%D0%B0-103246438349928"
                    class="social-icon"
                  >
                    <i class="mdi mdi-facebook"></i>
                  </a>
                </li>
              </ul>
            </div>
            <div class="clearfix"></div>
          </div>
        </div>
      </div>
    </div>
    <!--START FOOTER ALTER-->
  </div>
</template>
