<template>
    <div class="email-details">
        <div class="email-nav">
            <button @click="goBack" class="button-bck"><img src="../assets/icons/chevron_left_black_24dp.svg" alt="Newer" class="btn-icon-sm btn-icon-alt"> Back</button>
        </div>
        <h1 style="font-size:26px;margin-bottom:1rem;margin-left:1rem;">{{ message.subject }}</h1>
        <div class="profile-container">
            <div class="info-box">
            <img src="https://s3.amazonaws.com/cdn.officepuzzle.com/avatars/143.png" class="avatar-img">
            <p style="font-weight: bold;">{{ message.sender }}</p>
            <p style="font-size:12px; margin: 3px;"> -{{ message.email }}-</p>
          </div>
        <div class="date-box">
          <p>{{ message.date }}</p>
          <button class="btn star" style="margin-top: -13px;">
            <img src="../assets/icons/star_border_black_24dp.svg" alt="Not starred" class="btn-icon-sm btn-icon-alt btn-icon-hover message-btn-icon">
          </button>
        </div>
        </div>
      <p style="text-align: center;margin-top:12px;">{{ message.body }}</p>
      <div class="btn-container">
        <button class="btn action-btn" style="margin-top: -13px;"> Respond </button>
        <button class="btn action-btn" style="margin-top: -13px;"> Transfer </button>
      </div>
    </div>
  </template>

  <script>
  export default {
    props: {
      message: {
        type: Object,
        required: true
      }
    },
    methods: {
    goBack() {
      this.$emit('go-back');
    }
  }
  }
  </script>

  <style scoped>
  .email-details {
    margin-top: 20px;
    padding: 1rem;
  }
  .profile-container {
    display: flex;
    justify-content: space-around;
  }
  .info-box {
    display: flex;
  }
  .date-box {
    display: flex;
  }
  .avatar-img {
    width: 25px;
    height: 25px;
    border-radius: 50%;
  }
  .btn-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 3rem;
    border-top: 1px solid gray;
  }
  .action-btn {
    border-radius: 30px;
    width: 100px;
    height: 30px;
    border: 1px solid gray;
    margin: 1rem;
    margin-top: 1rem!important;
  }
  .email-nav {
    background-color: #fff;
    margin: 1rem;
    margin-bottom: 3rem!important;
  }
  .button-bck {
    border: none;
    background-color: #fff;
  }
  </style>
