<template>
  <div id="app">
    <h1>Masukan Gambar</h1>
    <FileDisplay :fileName="fileName" :imageURL="imageURL" />
    <FileInput @file-selected="handleFileSelected" />
  </div>
</template>

<script>
import FileInput from './FileInput.vue';
import FileDisplay from './ProfileImage.vue';

export default {
  components: {
    FileInput,
    FileDisplay
  },
  data() {
    return {
      fileName: '',
      imageURL: ''
    };
  },
  methods: {
    handleFileSelected(fileData) {
      this.fileName = fileData.fileName;
      this.imageURL = fileData.imageURL;
    }
  }
};
</script>

<style>
body{
  max-width: 600px;
  margin: 50px auto;
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>