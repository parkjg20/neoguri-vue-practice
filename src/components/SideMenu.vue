<template>
  <div class="side-menu-area">
    <h3>Features</h3>

    <ul class="side-menu-tabs">
      <li class="side-menu-tab"><a href="#/" >Home</a></li>
      <li class="side-menu-tab"><a href="#/data-bind">Data bind</a></li>
      <li class="side-menu-tab"><a href="#/event-listeners">Event Listening</a></li>
      <li class="side-menu-tab"><a href="#/modals">Modals</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SideMenu',
  props: {
    currentPath: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .side-menu-area {
    width: 15vw;
    min-width: 200px;
    flex-direction: column;
    padding: 32px 0;
    background-color: #8a8a8a;
    border-right: 3px solid #4a4a4a;
  }

  h3 {
    font-size: 28px;
    font-weight: 600;
  }

  .side-menu-tabs {
    text-align: left;
    margin-top: 16px;
  }

  .side-menu-tabs li {
    vertical-align: center;
    border-bottom: 1px solid #4a4a4a;
    cursor: pointer;
  }
  .side-menu-tabs li a {
    display: flex;
    padding: 12px 20px;
  }

  .side-menu-tabs li:last-child {
    border-bottom: none
  }

  .side-menu-tabs li.active,
  .side-menu-tabs li:hover {
    background-color: #4a4a4a;
    font-weight: bold;
    color: white;
  }

</style>
