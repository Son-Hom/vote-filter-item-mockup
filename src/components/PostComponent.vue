<template>
    <div class="container">
      <div class="search-wrapper">
        <input type="text" v-model="search" placeholder="Search title.."/>
            <label>Search title:</label>
      </div>
    </div>
    <div class="wrapper">
        <div class="card" v-for="post in filteredList" :key="post.id">
          <div class="votes">
            <div class="upvote" @click="post.votes++"></div>
            <div class="number-of-votes1" v-if="post.votes>=0 && post.votes<=10">{{post.votes}}</div>
            <div class="number-of-votes2" v-else-if="post.votes<0 && post.votes>=-10">{{post.votes}}</div>
            <div class="downvote" @click="post.votes--"></div>
          </div> 
          <a v-bind:href="post.link" target="_blank">
            <img v-bind:src="post.img"/>
            <small>posted by:{{ post.author }}</small>
            {{ post.title }}
          </a>
        </div>
      </div>
  </template>
  <script>
  import '../assets/style.css';
  import jsonData from '../data.json'
  export default{
    data(){
    return{
      search: '',
      data:jsonData,
      }
    },
    computed: {
      // filter
      filteredList() {
        return this.data.filter(post => {
          return post.title.toLowerCase().includes(this.search.toLowerCase())
        })
      }
    }
  };
  </script>
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  </style>
  