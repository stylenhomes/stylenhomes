<template>
    <div class="footer">
      <div class="footer-content">
        <div class="footer-left">
          <div v-for="section in leftSections" :key="section.title">
            <h4>{{ section.title }}</h4>
            <ul>
              <li v-for="item in section.items" :key="item">{{ item }}</li>
            </ul>
          </div>
        </div>
        <div class="footer-right">
          <img :src="qrCodeUrl" alt="QR Code" class="qr-code" />
          <div class="small-icons">
            <img v-for="(icon, index) in smallIcons" :key="index" :src="icon.url" @click="iconClick(icon.link)" class="small-icon" />
          </div>
        </div>
      </div>
      <p>About Us | Contact | Privacy Policy</p>
      <p>&copy; 2024 Company Name. All rights reserved.</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        leftSections: [
          {
            title: 'Section 1',
            items: ['Item 1', 'Item 2', 'Item 3', 'Item 4']
          },
          {
            title: 'Section 2',
            items: ['Item A', 'Item B', 'Item C', 'Item D']
          }
        ],
        qrCodeUrl: 'path/to/qr-code.png',
        smallIcons: [
          { url: 'path/to/icon1.png', link: 'https://link1.com' },
          { url: 'path/to/icon2.png', link: 'https://link2.com' },
          { url: 'path/to/icon3.png', link: 'https://link3.com' },
          { url: 'path/to/icon4.png', link: 'https://link4.com' },
          { url: 'path/to/icon5.png', link: 'https://link5.com' }
        ]
      };
    },
    methods: {
      iconClick(link) {
        window.location.href = link;
      }
    }
  };
  </script>
  
  <style scoped>
  .footer {
    background-color: #f8f8f8;
    padding: 20px 0;
    border-top: 1px solid #ddd;
    text-align: center;
  }
  .footer-content {
    display: flex;
    justify-content: space-between;
    padding-bottom: 20px;
  }
  .footer-left {
    display: flex;
    justify-content: space-around;
    width: 50%;
  }
  .footer-right {
    width: 50%;
    text-align: center;
  }
  .qr-code {
    width: 150px;
    height: 150px;
  }
  .small-icons {
    display: flex;
    justify-content: space-around;
    margin-top: 10px;
  }
  .small-icon {
    width: 50px;
    height: 50px;
    cursor: pointer;
  }
  </style>
  