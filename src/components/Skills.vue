<template>
  <div class="hello">
    <div class="holder">
      <form @submit.prevent="addSkill">
      <input type="text" placeholder="Enter a skill" v-model="skill">
      {{ skill }} 
      </form>
      <!-- allows us through interperlate to display input -->
      <ul>
      <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data, i) in skills" :key="i">{{i+1}}.{{data.skill}}
        <i class="fa fa-minus-circle" v-on:click="remove(i)"></i>
        </li>
      
      </transition-group>
      <!--transition group to use animation on the list -->
      </ul>
      <p> These are your skills!</p>
      <!-- <p v-if="skills.length >= 1">You have more than 1 skill</p>
      <p v-else>You need more skills bro</p> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skill: '',
      skills: [
        {"skill": "Vue.js"},
        {"skill": "Frontend Developer"},
        {"skill": "Backend Developer"},
        {"skill": "Full Stack Developer"}
      ]
      
    }
  },
  methods: {
    addSkill() {
      this.skills.push({skill: this.skill});
      this.skill = '';
      // set skill to empty string so any input would work     
    },
    remove(id) {
      this.skills.splice(id,1);
    }
  }

  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 /* if you have a lot of css make a css file and inlude inside style tag  src="./Skills.css" scoped> */
 @import "http://cdn.jsdelivr.net/npm/animate.css@3.5.1";
/* importing custom animation from 3rd party */
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";
 .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }

 </style> 
