<template>
  <layout-header></layout-header>
  <layout-sidebar></layout-sidebar>
  <div class="page-wrapper">
    <div class="content settings-content">
      <div class="page-header settings-pg-header">
        <div class="add-item d-flex">
          <div class="page-title">
            <h4>Settings</h4>
            <h6>Manage your settings on portal</h6>
          </div>
        </div>
        <ul class="table-top-head">
          <li>
            <a data-bs-toggle="tooltip" data-bs-placement="top" title="Refresh"
              ><i data-feather="rotate-ccw" class="feather-rotate-ccw"></i
            ></a>
          </li>
          <li>
            <a
              ref="collapseHeader"
              data-bs-toggle="tooltip"
              data-bs-placement="top"
              title="Collapse"
              @click="toggleCollapse"
            >
              <i data-feather="chevron-up" class="feather-chevron-up"></i>
            </a>
          </li>
        </ul>
      </div>
      <div class="row">
        <div class="col-xl-12">
          <div class="settings-wrapper d-flex">
            <div class="sidebars settings-sidebar theiaStickySidebar" id="sidebar2">
              <settings-sidebar></settings-sidebar>
            </div>
            <div class="settings-page-wrap">
              <form @submit.prevent="submitForm">
                <div class="setting-title">
                  <h4>Company Settings</h4>
                </div>
                <div class="company-info">
                  <div class="card-title-head">
                    <h6>
                      <span><vue-feather type="zap"></vue-feather></span>Company
                      Information
                    </h6>
                  </div>
                  <div class="row">
                    <div class="col-xl-4 col-lg-6 col-md-4">
                      <div class="mb-3">
                        <label class="form-label">Company Name</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-xl-4 col-lg-6 col-md-4">
                      <div class="mb-3">
                        <label class="form-label">Company Email Address</label>
                        <input type="email" class="form-control" />
                      </div>
                    </div>
                    <div class="col-md-4">
                      <div class="mb-3">
                        <label class="form-label">Phone Number</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-md-4">
                      <div class="mb-3">
                        <label class="form-label">Fax</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-md-4">
                      <div class="mb-3">
                        <label class="form-label">Website</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                  </div>
                </div>
                <div class="company-info company-images">
                  <div class="card-title-head">
                    <h6>
                      <span><vue-feather type="image"></vue-feather></span>Company Images
                    </h6>
                  </div>
                  <ul class="logo-company">
                    <li class="d-flex align-items-center">
                      <div class="logo-info">
                        <h6>Company Logo</h6>
                        <p>Upload Logo of your Company to display in website</p>
                      </div>
                      <div class="profile-pic-upload mb-0">
                        <div class="new-employee-field">
                          <div class="mb-0">
                            <div class="image-upload mb-0">
                              <input type="file" />
                              <div class="image-uploads">
                                <h4>
                                  <vue-feather type="upload"></vue-feather>Upload Photo
                                </h4>
                              </div>
                            </div>
                            <span
                              >For better preview recommended size is 450px x 450px. Max
                              size 5MB.</span
                            >
                          </div>
                        </div>
                      </div>
                      <div class="new-logo ms-auto">
                        <a href="javascript:void(0);"
                          ><img src="@/assets/img/logo-small.png" alt="Logo" /><span
                            ><vue-feather type="x"></vue-feather></span
                        ></a>
                      </div>
                    </li>
                    <li class="d-flex align-items-center">
                      <div class="logo-info">
                        <h6>Company Icon</h6>
                        <p>Upload Icon of your Company to display in website</p>
                      </div>
                      <div class="profile-pic-upload mb-0">
                        <div class="new-employee-field">
                          <div class="mb-0">
                            <div class="image-upload mb-0">
                              <input type="file" />
                              <div class="image-uploads">
                                <h4>
                                  <vue-feather type="upload"></vue-feather>Upload Photo
                                </h4>
                              </div>
                            </div>
                            <span
                              >For better preview recommended size is 450px x 450px. Max
                              size 5MB.</span
                            >
                          </div>
                        </div>
                      </div>
                      <div class="new-logo ms-auto">
                        <a href="javascript:void(0);"
                          ><img src="@/assets/img/logo-small.png" alt="Logo" /><span
                            ><vue-feather type="x"></vue-feather></span
                        ></a>
                      </div>
                    </li>
                    <li class="d-flex align-items-center">
                      <div class="logo-info">
                        <h6>Favicon</h6>
                        <p>Upload Favicon of your Company to display in website</p>
                      </div>
                      <div class="profile-pic-upload mb-0">
                        <div class="new-employee-field">
                          <div class="mb-0">
                            <div class="image-upload mb-0">
                              <input type="file" />
                              <div class="image-uploads">
                                <h4>
                                  <vue-feather type="upload"></vue-feather>Upload Photo
                                </h4>
                              </div>
                            </div>
                            <span
                              >For better preview recommended size is 450px x 450px. Max
                              size 5MB.</span
                            >
                          </div>
                        </div>
                      </div>
                      <div class="new-logo ms-auto">
                        <a href="javascript:void(0);"
                          ><img src="@/assets/img/logo-small.png" alt="Logo" /><span
                            ><vue-feather type="x"></vue-feather></span
                        ></a>
                      </div>
                    </li>
                    <li class="d-flex align-items-center">
                      <div class="logo-info">
                        <h6>Company Dark Logo</h6>
                        <p>Upload Logo of your Company to display in website</p>
                      </div>
                      <div class="profile-pic-upload mb-0">
                        <div class="new-employee-field">
                          <div class="mb-0">
                            <div class="image-upload mb-0">
                              <input type="file" />
                              <div class="image-uploads">
                                <h4>
                                  <vue-feather type="upload"></vue-feather>Upload Photo
                                </h4>
                              </div>
                            </div>
                            <span
                              >For better preview recommended size is 450px x 450px. Max
                              size 5MB.</span
                            >
                          </div>
                        </div>
                      </div>
                      <div class="new-logo ms-auto">
                        <a href="javascript:void(0);"
                          ><img src="@/assets/img/logo-small.png" alt="Logo" /><span
                            ><vue-feather type="x"></vue-feather></span
                        ></a>
                      </div>
                    </li>
                  </ul>
                </div>
                <div class="company-address">
                  <div class="card-title-head">
                    <h6>
                      <span><vue-feather type="map-pin"></vue-feather></span>Address
                    </h6>
                  </div>
                  <div class="row">
                    <div class="col-md-12">
                      <div class="mb-3">
                        <label class="form-label">Address</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-xl-3 col-lg-4 col-md-3">
                      <div class="mb-3">
                        <label class="form-label">Country</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-xl-3 col-lg-4 col-md-3">
                      <div class="mb-3">
                        <label class="form-label">State / Province</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-xl-3 col-lg-4 col-md-3">
                      <div class="mb-3">
                        <label class="form-label">City</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                    <div class="col-xl-3 col-lg-4 col-md-3">
                      <div class="mb-3">
                        <label class="form-label">Postal Code</label>
                        <input type="text" class="form-control" />
                      </div>
                    </div>
                  </div>
                </div>
                <div class="modal-footer-btn">
                  <button
                    type="button"
                    class="btn btn-cancel me-2"
                    data-bs-dismiss="modal"
                  >
                    Cancel
                  </button>
                  <button type="submit" class="btn btn-submit">Save Changes</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    submitForm() {
      this.$router.push("/settings/company-settings");
    },
    toggleCollapse() {
      const collapseHeader = this.$refs.collapseHeader;

      if (collapseHeader) {
        collapseHeader.classList.toggle("active");
        document.body.classList.toggle("header-collapse");
      }
    },
  },
};
</script>
