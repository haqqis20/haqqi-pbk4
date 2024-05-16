<template>
    <div class="file-display">
      <img v-if="imageURL" :src="imageURL" alt="Uploaded Image" class="preview-image" />
      <p v-if="fileName" class="file-name">{{ fileName }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      fileName: {
        type: String,
        required: true
      },
      imageURL: {
        type: String,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .file-display {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px;
  }
  
  .file-name {
    font-size: 1.2em;
    color: #333;
    margin-bottom: 10px;
  }
  
  .preview-image {
    border: 2px solid #007BFF;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
  }
  
  .preview-image:hover {
    transform: scale(1.05);
  }
  
  img {
    
    height: 150px;
    width: 150px;
    border-radius: 50%;
    object-fit: cover;
    background: #dfdfdf;
  }
  </style>
  