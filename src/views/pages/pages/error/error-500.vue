<template>
  <div class="error-page">
    <div class="error-box">
      <div class="error-img">
        <img src="@/assets/img/authentication/error-500.png" class="img-fluid" alt="" />
      </div>
      <h3 class="h2 mb-3">Oops, something went wrong</h3>
      <p>
        Server Error 500. We apologise and are fixing the problem Please try again at a
        later stage
      </p>
      <router-link to="/dashboard" class="btn btn-primary"
        >Back to Dashboard</router-link
      >
    </div>
  </div>
</template>
