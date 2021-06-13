<script>
/**
 * Login component
 */
export default {
  name: "Login"
};
</script>

<template>
  <div class="bg-account-pages py-4 py-sm-0">
    <div class="account-home-btn d-none d-sm-block">
      <a href="/" class="text-white">
        <i class="mdi mdi-home h1"></i>
      </a>
    </div>

    <section class="height-100vh">
      <div class="display-table">
        <div class="display-table-cell">
          <div class="container">
            <div class="row justify-content-center">
              <div class="col-lg-5">
                <div class="card account-card">
                  <div class="card-body">
                    <div class="text-center mt-3">
                      <h3 class="font-weight-bold">
                        <a
                          href="/"
                          class="text-dark text-uppercase account-pages-logo"
                        >
                          <img src="/logo.png" width="40px" />
                        </a>
                      </h3>
                      <p class="text-muted">Админ нэвтрэх</p>
                    </div>
                    <div class="p-3">
                      <form>
                        <div class="form-group">
                          <label for="username">Имэйл</label>
                          <input
                            type="text"
                            class="form-control"
                            id="username"
                            placeholder="Имэйл"
                            v-model="form.email"
                          />
                        </div>

                        <div class="form-group">
                          <label for="userpassword">Нууц үг</label>
                          <input
                            type="password"
                            class="form-control"
                            id="userpassword"
                            placeholder="Нууц үг"
                            v-model="form.password"
                          />
                        </div>

                        <div class="custom-control custom-checkbox">
                          <input
                            type="checkbox"
                            class="custom-control-input"
                            id="customControlInline"
                          />
                          <label
                            class="custom-control-label"
                            for="customControlInline"
                            >Сануулах</label
                          >
                        </div>

                        <div class="mt-3">
                          <button
                            type="button"
                            @click="login"
                            class="btn btn-custom btn-block"
                          >
                            Нэвтрэх
                          </button>
                        </div>
                      </form>
                    </div>
                  </div>
                </div>
                <!-- end card -->
              </div>
              <!-- end col -->
            </div>
            <!-- end row -->
          </div>
        </div>
      </div>
    </section>
    <!-- end account-pages  -->
  </div>
</template>
<script>
export default {
  middleware: "no_auth",
  data() {
    return {
      form: {
        email: null,
        password: null
      }
    };
  },
  methods: {
    login() {
      this.$axios
        .$post("/login", this.form)
        .then(({ token, expiresIn }) => {
          this.$store.dispatch("user/setToken", { token, expiresIn });
          this.$router.push("/admin");
        })
        .catch(errors => {});
    }
  }
};
</script>
