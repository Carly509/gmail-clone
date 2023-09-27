<template>
  <div id="app" class="content">
    <div v-if="selectedEmailId === null">
    <inbox-msg v-for="record in records" :key="record.id" :message="record" @select-email="selectedEmailId = $event"></inbox-msg>
    </div>
    <div v-if="selectedEmailId !== null">
    <email-details :message="getEmailById(selectedEmailId)" @go-back="goBackToInbox"></email-details>
    </div>
  </div>
</template>

<script>
import Inbox from './components/Inbox.vue';
import records from '../data/records.json';
import EmailDetails from './components/EmailDetails.vue';

export default {
  name: 'app',
  components: {
    'inbox-msg': Inbox,
    'email-details': EmailDetails
  },
  data: function() {
    return {
      records: records,
      selectedEmailId: null,
  }
 },
  methods: {
    getEmailById(id) {
      return this.records.find(record => record.id === id);
    },
    goBackToInbox() {
      this.selectedEmailId = null;
    }
  }
}
</script>

<style>
</style>
