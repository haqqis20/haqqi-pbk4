<template>
    <div class="file-input">
      <label for="file-upload" class="custom-file-upload">
        Pilih Gambar
      </label>
      <input id="file-upload" type="file" @change="onFileChange" accept="image/*" />
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      onFileChange(event) {
        const file = event.target.files[0];
        if (file) {
          this.$emit('file-selected', {
            fileName: file.name,
            imageURL: URL.createObjectURL(file)
          });
        } else {
          this.$emit('file-selected', {
            fileName: '',
            imageURL: ''
          });
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .file-input {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px;
  }
  
  .custom-file-upload {
    display: inline-block;
    padding: 10px 20px;
    cursor: pointer;
    background-color: #007BFF;
    color: white;
    border-radius: 5px;
    transition: background-color 0.3s ease;
  }
  
  .custom-file-upload:hover {
    background-color: #0056b3;
  }
  
  input[type="file"] {
    display: none;
  }
  </style>