<template>
  <div class="mail">
   <div class="inbox-message-item" :class="message.read ? 'inbox-message-item' : 'inbox-message-item message-default-unread'" @click="selectEmail">

    <div class="checkbox" style="margin-right: -12px;" >
      <button class="btn">
        <img src="../assets/icons/check_box_outline_blank_black_24dp.svg" alt="Select" class="btn-icon-sm btn-icon-alt btn-icon-hover message-btn-icon">
      </button>
    </div>

    <div class="message-group-hidden">
      <button class="btn-alt btn-nofill drag-indicator" >
        <img src="../assets/icons/drag_indicator_black_24dp.svg" alt="Drag" class="btn-icon-sm btn-icon-alt btn-icon-disabled" >
      </button>
    </div>

    <button class="btn star" style="margin: 0;">
      <img src="../assets/icons/star_border_black_24dp.svg" alt="Not starred" class="btn-icon-sm btn-icon-alt btn-icon-hover message-btn-icon">
    </button>

    <div class="message-default" >

      <div :class="['message-sender', 'message-content', message.read ? '' : 'unread']" >
        <span >{{ message.sender }}</span>
      </div>

      <div :class="['message-subject', 'message-content', message.read ? '' : 'unread']">
        <span>{{ message.subject }}</span>
      </div>

      <div class="message-seperator message-content"> - </div>

      <div class="message-body message-content">
        <span> {{ message.body }}</span>
      </div>

      <div class="gap message-content" > &nbsp; </div>

      <div :class="['message-date', 'center-text', message.read ? '' : 'unread']">
        <span>{{ message.date }}</span>
      </div>

    </div>

    <div class="message-group-hidden" >
      <div class="inbox-message-item-options">
        <button class="btn">
          <img src="../assets/icons/archive_black_24dp.svg" alt="Archive" class="btn-icon-sm btn-icon-alt btn-icon-hover">
        </button>

        <button class="btn">
          <img src="../assets/icons/delete_black_24dp.svg" alt="Delete" class="btn-icon-sm btn-icon-alt btn-icon-hover">
        </button>

        <button class="btn">
          <img src="../assets/icons/mark_as_unread_black_24dp.svg" alt="Mark as unread" class="btn-icon-sm btn-icon-alt btn-icon-hover">
        </button>

        <button class="btn">
          <img src="../assets/icons/access_time_filled_black_24dp.svg" alt="Snooze" class="btn-icon-sm btn-icon-alt btn-icon-hover">
        </button>
      </div>
    </div>
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
    selectEmail() {
      this.$emit('select-email', this.message.id);
    }
  }
}
</script>
