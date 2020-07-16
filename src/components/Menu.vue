<template>
    <div id="menu">
        <ul class="card-list">
            <li v-for="message in messages" v-bind:key="message">
                <MessageCard :info= message></MessageCard>
            </li>
        </ul>
    </div>
</template>

<script>
import MessageCard from './Message-Card.vue'

export default {
  name: 'menu',
  data(){
    return{
        messages:[{
          name: '点点点',
          lon: 101.223,
          lat:  28.333
        },{
          name: '哦哦哦',
          lon: 101.223,
          lat:  29.333
        },{
          name: '嗯嗯嗯',
          lon: 102.223,
          lat:  28.333
        },{
          name: '哈哈哈',
          lon: 103.223,
          lat:  28.333
        }]
    }
  },
  methods:{

  },
  mounted(){

  },
  components: {
    MessageCard
  }
}
</script>
<style scoped>
    .menu{
      height: 90%;
      width: 300px;
      background-color: #ffffff;
      border-radius: 4px;
    }
    .card-list{
          list-style: none;
    padding: 0;
    margin: 0;
    }
</style>