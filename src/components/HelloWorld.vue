<template>
  <div id="hello-world">
    <div class="tab-container">
      <div class="tabs">
        <div class="tab" v-bind:class="{selected : activeTabIndex === 0}" v-on:click="activeTabIndex = 0">Tab 0</div>
        <div class="tab" v-bind:class="{selected : activeTabIndex === 1}" v-on:click="activeTabIndex = 1">Tab 1</div>
        <div class="tab" v-bind:class="{selected : activeTabIndex === 2}" v-on:click="activeTabIndex = 2">Tab 2</div>
        <div class="tab" v-bind:class="{selected : activeTabIndex === 3}" v-on:click="activeTabIndex = 3">Tab 3</div>
      </div>
      <div class="underline-container">
        <div class="tab__underline" v-bind:style="{marginLeft: 25 * activeTabIndex + '%'}"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    activeTabIndex: 0
  })
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .tab-container {
    width: 40%;
    margin: 0 auto;

    display: -webkit-flex; /* For Safari */
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
  }

  .tabs {
    width: 100%;

    display: -webkit-flex; /* For Safari */
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
  }

  .tab {
    color: #808080;
    font-size: 1.2em;
    padding: 0.4em;
    margin: 0 0.4em;

    cursor: pointer;

    flex-grow: 1;

    /* Make text content not selectable */
    user-select: none;
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    -o-user-select: none;
  }

  .tab.selected {
    color: #000000;

    transition: .3s;
  }

  .underline-container {
    height: 0.25em;
    width: 100%;
  }

  .tab__underline {
    height: 0.25em;
    width: 25%;
    background-color: #000000;
    border-radius: 0.125em;

    transition: .3s;
  }
</style>
