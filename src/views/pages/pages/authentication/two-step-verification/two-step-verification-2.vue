<template>
  <div class="account-page">
    <div class="account-content">
      <div class="login-wrapper">
        <div class="login-content">
          <div class="login-userset">
            <div class="login-userset">
              <div class="login-logo logo-normal">
                <img src="@/assets/img/logo.png" alt="img" />
              </div>
            </div>
            <router-link to="/dashboard" class="login-logo logo-white">
              <img src="@/assets/img/logo-white.png" alt="" />
            </router-link>
            <div class="login-userheading">
              <h3>Login With Your Email Address</h3>
              <h4 class="verfy-mail-content">
                We sent a verification code to your email. Enter the code from the email
                in the field below
              </h4>
            </div>
            <form @submit.prevent="submitForm" class="digit-group">
              <div class="wallet-add">
                <div class="otp-box">
                  <div class="forms-block text-center">
                    <input type="text" id="digit-1" maxlength="1" value="" />
                    <input type="text" id="digit-2" maxlength="1" value="" />
                    <input type="text" id="digit-3" maxlength="1" value="" />
                    <input type="text" id="digit-4" maxlength="1" value="" />
                  </div>
                </div>
              </div>
              <div class="Otp-expire text-center">
                <p>Otp will expire in 09 :10</p>
              </div>
              <div class="form-login mt-4">
                <button type="submit" class="btn btn-login">Verify My Account</button>
              </div>
            </form>
            <div
              class="my-4 d-flex justify-content-center align-items-center copyright-text"
            >
              <p>Copyright &copy; {{ new Date().getFullYear() }} DreamsPOS. All rights reserved</p>
            </div>
          </div>
        </div>
        <div class="login-img">
          <img src="@/assets/img/authentication/step-two.png" alt="img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    submitForm() {
      this.$router.push("/dashboard");
    },
  },

}
</script>