<template>
  <div class="homescreen padded-container">
    <router-link :to="app.route" class="app" v-for="app in apps" v-bind:key="app.route">
      <div v-bind:class="app.backgroundClass">
        <svg v-html="app.icon" v-bind:class="app.iconClass" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></svg>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'homescreen',
  computed: {
    apps: function() {
      return [
        // SMS
        {
          route: '/sms',
          backgroundClass: 'app-icon blue-color',
          icon: '<path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"></path>',
          iconClass: 'feather feather-message-circle'
        },
        // CONTACTS
        {
          route: '/contacts',
          backgroundClass: 'app-icon peach-color',
          icon: '<path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path>',
          iconClass: 'feather feather-users'
        },
        // BANKING
        {
          route: '/bank',
          backgroundClass: 'app-icon orange-color',
          icon: '<line x1="12" y1="1" x2="12" y2="23"></line><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path>',
          iconClass: 'feather feather-dollar-sign'
        },
        // EMERGENCY
        /*{
          route: '/emergency',
          backgroundClass: 'app-icon red-color',
          icon: '<path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path><line x1="12" y1="9" x2="12" y2="13"></line><line x1="12" y1="17" x2="12.01" y2="17"></line>',
          iconClass: 'feather feather-alert-triangle'
        }*/
      ]
    }
  }
}
</script>

<style>
  .homescreen {
    width: 100%;
  }

  .app {
    width: 25%;
    text-decoration: none;
    color: #000;
    display: inline-block;
    box-sizing: border-box;
    padding: 10px;
  }

  .app-icon {
    width: 26px;
    height: 26px;
    text-align: center;
    padding: 10px;
    border-radius: 6px;
  }

  .peach-color {
    color: #fff;
    background-image: linear-gradient( 0deg,  rgba(255,190,32,1) 0.6%, rgba(251,112,71,1) 124.3% );
  }

  .blue-color {
    color: #fff;
    background: linear-gradient(to bottom, #2980B9, #6DD5FA);
  }

  .orange-color {
    color: #fff;
    background-image: linear-gradient(to bottom, #fe5196 0%, #f77062 100%);
  }

  .red-color {
    color: #fff;
    background-image: linear-gradient(to bottom, #c0392b 0%, #e74c3c 100%);
  }
</style>
