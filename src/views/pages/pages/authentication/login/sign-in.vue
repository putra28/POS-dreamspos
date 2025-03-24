<template>
  <div class="account-page">
    <div class="account-content">
      <div class="login-wrapper bg-img">
        <div class="login-content">
          <Form @submit="onSubmit" :validation-schema="schema" v-slot="{ errors }">
            <div class="login-userset">
              <div class="login-logo logo-normal">
                <img src="@/assets/img/logo.png" alt="img" />
              </div>
              <router-link to="/dashboard" class="login-logo logo-white">
                <img src="@/assets/img/logo-white.png" alt="" />
              </router-link>
              <div class="login-userheading">
                <h3>Sign In</h3>
                <h4>Gunakan No. Telp dan Password</h4>
              </div>
              <div class="form-login mb-3">
                <label class="form-label">No. Telp</label>
                <div class="form-addons">
                  <Field
                    name="email"
                    type="text"
                    value="081234567890"
                    class="form-control"
                    :class="{ 'is-invalid': errors.email }"
                  />
                  <div class="invalid-feedback">{{ errors.email }}</div>
                  <div class="emailshow text-danger" id="email"></div>
                  <img src="@/assets/img/icons/mail.svg" alt="img" />
                </div>
              </div>
              <div class="form-login mb-3">
                <label class="form-label">Password</label>
                <div class="pass-group">
                  <Field
                    name="password"
                    :type="showPassword ? 'text' : 'password'"
                    value="password"
                    class="form-control pass-input mt-2"
                    :class="{ 'is-invalid': errors.password }"
                  />
                  <span @click="toggleShow" class="toggle-password">
                    <i
                      :class="{
                        'fas fa-eye': showPassword,
                        'fas fa-eye-slash': !showPassword,
                      }"
                    ></i>
                  </span>
                  <div class="invalid-feedback">{{ errors.password }}</div>
                  <div class="emailshow text-danger" id="password"></div>
                </div>
              </div>
              <div class="form-login authentication-check">
                <div class="row">
                  <div class="col-12 d-flex align-items-center justify-content-between">
                    <div class="text-end">
                      <router-link class="forgot-link" to="/forgot-password"
                        >Forgot Password?</router-link
                      >
                    </div>
                  </div>
                </div>
              </div>
              <div class="form-login">
                <button type="submit" class="btn btn-login">Sign In</button>
              </div>
              <div class="signinform">
                <h4>
                  New on our platform?<router-link to="/register" class="hover-a">
                    Create an account</router-link
                  >
                </h4>
              </div>
              <div class="form-setlogin or-text">
                <h4>OR</h4>
              </div>
              <div class="form-sociallink">
                <ul class="d-flex">
                  <li>
                    <a href="javascript:void(0);" class="facebook-logo">
                      <img src="@/assets/img/icons/facebook-logo.svg" alt="Facebook" />
                    </a>
                  </li>
                  <li>
                    <a href="javascript:void(0);">
                      <img src="@/assets/img/icons/google.png" alt="Google" />
                    </a>
                  </li>
                  <li>
                    <a href="javascript:void(0);" class="apple-logo">
                      <img src="@/assets/img/icons/apple-logo.svg" alt="Apple" />
                    </a>
                  </li>
                </ul>
                <div
                  class="my-4 d-flex justify-content-center align-items-center copyright-text"
                >
                  <p>
                    Copyright &copy; {{ new Date().getFullYear() }} DreamsPOS. All rights
                    reserved
                  </p>
                </div>
              </div>
            </div>
          </Form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { ref } from "vue";
import { useRouter } from "vue-router";
import { Form, Field } from "vee-validate";
import * as Yup from "yup";

export default {
  components: {
    Form,
    Field,
  },
  setup() {
    const router = useRouter();
    const showPassword = ref(false);
    const emailError = ref("");
    const passwordError = ref("");

    const schema = Yup.object().shape({
      email: Yup.string().required("Data tidak boleh kosong"),
      password: Yup.string().required("Password tidak boleh kosong"),
    });

    const toggleShow = () => {
      showPassword.value = !showPassword.value;
    };

    const onSubmit = async (values) => {
      document.getElementById("email").innerHTML = "";
      document.getElementById("password").innerHTML = "";

      try {
        const response = await fetch("http://localhost:1111/api/users/login", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            p_contactUsers: values.email,
            p_passwordUsers: values.password,
          }),
        });

        const data = await response.json();

        if (!response.ok) {
          if (data.message.includes("Akun")) {
            document.getElementById("email").innerHTML = "Akun tidak ditemukan atau tidak aktif, coba lagi";
          } else if (data.message.includes("Password")) {
            document.getElementById("password").innerHTML = "Password salah, coba lagi";
          }
          return;
        }

        // ✅ Menyimpan data secara terpisah di localStorage
        localStorage.setItem("id_user", data.data.id_user);
        localStorage.setItem("nama_user", data.data.nama_user);
        localStorage.setItem("contact_user", data.data.contact_user);
        localStorage.setItem("role_user", data.data.role_user);
        localStorage.setItem("status_user", data.data.status_user);
        localStorage.setItem("created_at", data.data.created_at);
        localStorage.setItem("updated_at", data.data.updated_at);

        localStorage.setItem("userData", JSON.stringify(data.data));
        router.push("/dashboard");
      } catch (error) {
        console.error("Error:", error);
        document.getElementById("email").innerHTML = "Terjadi kesalahan pada server.";
      }
    };

    return {
      schema,
      onSubmit,
      showPassword,
      toggleShow,
      emailError,
      passwordError,
    };
  },
};
</script>
