<template>
  <div id="Inicio">
    <body class="bg-dark bg-gradient">
      <div id="layoutAuthentication">
        <div id="layoutAuthentication_content">
          <main>
            <div class="container">
              <div class="row justify-content-center">
                <div class="col-lg-5">
                  <div class="card shadow-lg border-0 rounded-lg mt-5">
                    <div class="card-header">
                      <h3 class="text-center font-weight-light my-4">
                        Iniciar sesión
                      </h3>
                    </div>
                    <div class="card-body">
                      <form v-on:submit.prevent="iniciar">
                        <div class="form-floating mb-3">
                          <input
                            class="form-control"
                            id="inputEmail"
                            type="email"
                            placeholder=""
                            v-model="email"
                          />
                          <label for="inputEmail">Correo electrónico</label>
                        </div>
                        <div class="form-floating mb-3">
                          <input
                            class="form-control"
                            id="inputPassword"
                            type="password"
                            placeholder=""
                            v-model="password"
                          />
                          <label for="inputPassword">Contraseña</label>
                        </div>
                        <div
                          class="
                            d-flex
                            align-items-center
                            justify-content-center
                            mt-4
                            mb-0
                          "
                        >
                          <input
                            type="submit"
                            class="btn btn-primary"
                            @click="login"
                            value="Iniciar sesión"
                          />
                        </div>
                      </form>
                      <div class="alert alert-danger" role="alert" v-if="error">
                        {{ error_msg }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </main>
        </div>
      </div>
    </body>
  </div>
</template>

<script>
import axios from "axios";
import Swal from "sweetalert2";
export default {
  name: "Inicio",
  components: {},
  data: function () {
    return {
      email: "",
      password: "",
      error: false,
      error_msg: "",
    };
  },
  methods: {
    iniciar() {
      let json = {
        email: this.email,
        password: this.password,
      };
      axios.post("https://ferremax.herokuapp.com/login/", json).then((data) => {
        if (data.data.status == "ok") {
          this.InicioSesion();
          localStorage.setItem("token", data.data.token);
          console.log(localStorage.getItem("token"));
          this.$router.push("/information");
        } else {
        this.InicioFallido(); 
        }
      });
     
      this.$router.push("/");
    },
    InicioSesion() {
      Swal.fire({
        icon: "success",
        title: "Inicio de sesion exitoso.",
      });
    },
    InicioFallido() {
      Swal.fire({
        icon: "error",
        title: "Usuario o contraseña incorrecto.",
      });
    },    
  },
};
</script>

<style scoped>
.mt-auto {
  margin-top: auto !important;
}
#layoutAuthentication_footer {
  min-width: 0;
  padding: 20px;
}
.px-4 {
  padding-right: 1.5rem !important;
  padding-left: 1.5rem !important;
}
.text-muted {
  --bs-text-opacity: 1;
  color: #6c757d !important;
}
body {
  height: 100vh;
}
</style>