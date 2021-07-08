<template>
  <div class="tabs">
    <h1 class="tabs__heading">{{ data.mainHeading }}</h1>
    <button class="tabs__buttons" 
    v-for="(tab, index) in data.tabs" :key="`tab${index}`"
    :class="{'tabs__buttons--active': activeTab === index}"
    @click="setActiveTab(index)">{{ tab.tabName }}</button>
    
    <div class="tabs-content" 
    v-for="(tab, index) in data.tabs" 
    :key="`data${index}`"
    :class="{'tabs-content--hidden': index !== activeTab}">
      <h2 class="tabs-content__heading">{{ tab.tabHeading }}</h2>
      <p class="tabs-content__text">{{ tab.tabDescription }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tabs",
  props: {
    data: {}
  },
  data() {
    return {
      activeTab: 0,
    }
  },
  methods: {
    setActiveTab(tabIndex) {
      this.activeTab = tabIndex
    }
  }
}

</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&family=Roboto&display=swap');

.tabs {
  margin: 100px 10px;
  padding: 0 30px;
  font-family: 'Roboto', sans-serif;

  @media screen and (max-width: 768px) {
    padding: 0 10px;
  }

  &__heading {
    text-transform: uppercase;
    color: $mint;
    font-size: 20px;
    font-weight: bold;
    margin: 60px 0 30px;  
  }

  &__buttons {
    background: none;
    color: $pink;
    border: none;
    font: inherit;
    cursor: pointer;
    outline: inherit;
    text-transform: uppercase;
    font-weight: bold;
    font-size: 17px;
    padding: 0 10px;

    @media screen and (max-width: 768px) {
      font-size: 15px;
      padding: 7px;
    }

    &--active {
      color: $white;
    }
  }

  &-content {
    width: 63%;
    color: $white;
    position: absolute;
    left: 19%;

    @media screen and (max-width: 768px) {
      text-align: left;
      width: 80%;
      left: 10%;
      margin-top: 20px;
    }

    &__heading {
      margin: 60px 0 30px;
      font-weight: bold;
      font-size: 35px;
    }

    &__text {
    font-size: 18px;
    }

    &--hidden {
      display: none;
    }
  }
}
</style>