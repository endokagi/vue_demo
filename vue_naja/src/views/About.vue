<script>
import ToggleSidebar from "@/components/toggle_sidebar";

export default {
  data() {
    return {
      previewImage: null,
    };
  },
  methods: {
    selectImage() {
      this.$refs.fileInput.click();
    },
    pickFile() {
      if (confirm("Are you sure to add?")) {
        let input = this.$refs.fileInput;
        let file = input.files;
        if (file && file[0]) {
          let reader = new FileReader();
          reader.onload = (e) => {
            this.previewImage = e.target.result;
          };
          reader.readAsDataURL(file[0]);
          this.$emit("input", file[0]);
        }
      }
    },
  },
  components: { ToggleSidebar },
};
</script>


<template>
  <div class="container">
    <h1>About</h1>
    <img src="../assets/logo.png" class="rounded mx-auto d-block" alt="wasd" />

    <div>
      <input ref="fileInput" type="file" @input="pickFile" />
      <div
        v-if="selectImage == false "
        class="imagePreviewWrapper"
        :style="{
          'background-image': `url('~@/assets/defult-user-image.png')`,
        }"
      ></div>
      <div
        v-else
        class="imagePreviewWrapper"
        :style="{ 'background-image': `url(${previewImage})` }"
        @click="selectImage"
      ></div>
    </div>
    <div>
      <ToggleSidebar />
    </div>
  </div>
</template>

<style scoped>
.imagePreviewWrapper {
  width: 250px;
  height: 250px;
  display: block;
  cursor: pointer;
  margin: 0 auto 30px;
  background-size: cover;
  background-position: center center;
}
</style>