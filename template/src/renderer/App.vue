<template>
<div id="app" style="position: relative;">
  <h1 class="ms-font-su ms-fontColor-white ms-bgColor-purple noselect banner">
    {{ name }}
    <div class="subtitle">Lorem ipsum dolar sit</div>
  </h1>
  <div class="main-content">
    <router-view></router-view>
  </div>
</div>
</template>

<script>
{{#isEnabled plugins 'vue-router'}}
{{else}}
  import LandingPage from '@/components/LandingPage'

{{/isEnabled}}
  export default {
    name: '{{ name }}'{{#isEnabled plugins 'vue-router'}}{{else}},{{/isEnabled}}
{{#isEnabled plugins 'vue-router'}}
{{else}}
    components: {
      LandingPage
    }
{{/isEnabled}}
  }
</script>

<style>
.banner {
  margin: 0;
  padding: 80px 20px 20px 20px;
  -webkit-app-region: drag;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 10000
}

  .noselect {
  cursor: pointer;
  -webkit-touch-callout: none; /* iOS Safari */
    -webkit-user-select: none; /* Safari */
     -khtml-user-select: none; /* Konqueror HTML */
       -moz-user-select: none; /* Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
            user-select: none; /* Non-prefixed version, currently
                                  supported by Chrome and Opera */
}

body {
  margin: 0;
  padding: 0;
  background: #fafafa;
}

.main-content {
  padding-top: 170px;
}

.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 20px;
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    z-index: 10;
}

.subtitle {
  font-size: 16px;
  margin-top: -5px;
}
</style>
