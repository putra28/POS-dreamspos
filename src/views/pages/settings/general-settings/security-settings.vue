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
              <div class="setting-title">
                <h4>Security</h4>
              </div>
              <div class="security-settings">
                <ul>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="eye-off"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Password</h5>
                        <p>Last Changed 22 July 2023, 10:30 AM</p>
                      </div>
                    </div>
                    <div class="security-btn">
                      <a href="javascript:void(0);" class="btn btn-primary"
                        >Change Password</a
                      >
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="shield"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Two Factor</h5>
                        <p>Receive codes via SMS or email every time you login</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <a href="javascript:void(0);" class="btn btn-danger">Disable</a>
                      <div
                        class="status-toggle modal-status d-flex justify-content-between align-items-center ms-2"
                      >
                        <input type="checkbox" id="user3" class="check" checked />
                        <label for="user3" class="checktoggle"> </label>
                      </div>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="shield"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Google Authentication</h5>
                        <p>Connect to Google</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <span class="badges-connected">Connected</span>
                      <div
                        class="status-toggle modal-status d-flex justify-content-between align-items-center ms-2"
                      >
                        <input type="checkbox" id="user4" class="check" checked />
                        <label for="user4" class="checktoggle"> </label>
                      </div>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="phone"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Phone Number Verification</h5>
                        <p>Verified Mobile Number : +81699799974</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <span><i class="fa fa-check-circle me-2"></i></span>
                      <a href="javascript:void(0);" class="btn btn-primary">Change</a>
                      <a href="javascript:void(0);" class="remove-red ms-2">Remove</a>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="mail"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Email Verification</h5>
                        <p>Verified Email : info@example.com</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <span><i class="fa fa-check-circle me-2"></i></span>
                      <a href="javascript:void(0);" class="btn btn-primary">Change</a>
                      <a href="javascript:void(0);" class="remove-red ms-2">Remove</a>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="tool"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Device Management</h5>
                        <p>Last Changed 22 July 2023, 10:30 AM</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <a href="javascript:void(0);" class="manage-btn">Manage</a>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="box"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Account Activity</h5>
                        <p>Last Changed 25 July 2023, 11:00 AM</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <a href="javascript:void(0);" class="manage-btn">View</a>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="slash"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Deactivate Account</h5>
                        <p>Last Changed 21 July 2023, 09:37 AM</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <a href="javascript:void(0);" class="manage-btn">Deactivate</a>
                    </div>
                  </li>
                  <li>
                    <div class="security-type">
                      <span class="security-icon"
                        ><vue-feather type="trash-2"></vue-feather
                      ></span>
                      <div class="security-title">
                        <h5>Delete Account</h5>
                        <p>Last Changed 26 July 2023, 11:40 AM</p>
                      </div>
                    </div>
                    <div class="security-btn d-flex align-items-center">
                      <a href="javascript:void(0);" class="btn btn-danger">Delete</a>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  methods: {
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
