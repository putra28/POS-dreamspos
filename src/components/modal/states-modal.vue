<template>
  <!-- Add State -->
  <div class="modal fade" id="add-units">
    <div class="modal-dialog modal-dialog-centered custom-modal-two">
      <div class="modal-content">
        <div class="page-wrapper-new p-0">
          <div class="content">
            <div class="modal-header border-0 custom-modal-header">
              <div class="page-title">
                <h4>Add State</h4>
              </div>
              <button
                type="button"
                class="close"
                data-bs-dismiss="modal"
                aria-label="Close"
              >
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="modal-body custom-modal-body">
              <form @submit.prevent="submitForm">
                <div class="row">
                  <div class="col-lg-6">
                    <div class="input-blocks">
                      <label>State Name</label>
                      <input type="text" class="form-control" />
                    </div>
                  </div>
                  <div class="col-lg-6">
                    <div class="input-blocks">
                      <label>Country</label>
                      <input type="text" class="form-control" />
                    </div>
                  </div>

                  <div class="row">
                    <!-- Editor -->
                    <div class="col-md-12">
                      <div class="edit-add card">
                        <div class="edit-add">
                          <label>Description</label>
                        </div>
                        <div class="card-body-list">
                          <editor v-model="content" />
                        </div>
                        <p>Maximum 600 Characters</p>
                      </div>
                    </div>
                    <!-- /Editor -->
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
                  <button type="submit" class="btn btn-submit">Submit</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- /Add State -->

  <!-- Edit State -->
  <div class="modal fade" id="edit-units">
    <div class="modal-dialog modal-dialog-centered custom-modal-two">
      <div class="modal-content">
        <div class="page-wrapper-new p-0">
          <div class="content">
            <div class="modal-header border-0 custom-modal-header">
              <div class="page-title">
                <h4>Edit State</h4>
              </div>
              <button
                type="button"
                class="close"
                data-bs-dismiss="modal"
                aria-label="Close"
              >
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="modal-body custom-modal-body">
              <form @submit.prevent="submitForm">
                <div class="row">
                  <div class="col-lg-6">
                    <div class="input-blocks">
                      <label>State Name</label>
                      <input type="text" placeholder="Beijing" />
                    </div>
                  </div>
                  <div class="col-lg-6">
                    <div class="input-blocks">
                      <label>Country</label>
                      <input type="text" placeholder="China" />
                    </div>
                  </div>

                  <div class="row">
                    <!-- Editor -->
                    <div class="col-md-12">
                      <div class="edit-add card">
                        <div class="edit-add">
                          <label>Description</label>
                        </div>
                        <div class="card-body-list">
                          <editor v-model="contentOne" />
                        </div>
                        <p>Maximum 600 Characters</p>
                      </div>
                    </div>
                    <!-- /Editor -->
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
                  <button type="submit" class="btn btn-submit">Submit</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- /Edit State -->
</template>
<script>
import Editor from "@tinymce/tinymce-vue";
export default {
  components: {
    editor: Editor,
  },
  methods: {
    submitForm() {
      this.$router.push("/places/states");
    },
  },
  data() {
    return {
      content: "Type your message",
      contentOne: "Type your message",
    };
  },
  name: "text-editor",
};
</script>
