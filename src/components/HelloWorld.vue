<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="marquee">
      <ul>
        <li v-for="(item,index) in colors.concat(colors)" :key="index" :style="{background: item.color}">
          {{ item.id }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      colors: [{
        color: '#E65D6E',
        id: '1'
      },{
        color: '#30B08F',
        id: '2'
      },{
        color: '#4AB7BD',
        id: '3'
      },{
        color: '#FEC171',
        id: '4'
      },{
        color: '#1890ff',
        id: '5'
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .marquee{
    width: 1000px;
    height: 200px;
    margin: 20px auto;
    overflow: hidden;
  }
  ul{
    margin: 0;
    padding: 0;
    width: 200%;
    height: 100%;
    list-style: none;
    animation: carousel 10s linear infinite;
    position: relative;
  }
  ul li{
    float: left;
    width: 200px;
    height: 100%;
    text-align: center;
    line-height: 200px;
    font-size: 30px;
  }
  @keyframes carousel {
    from {
      left: 0;
    }
    to {
      left: -1000px;
    }
  }
</style>
