<template>
  <div class="about">
    <h1> Hello {{their_name}}, This is the about page</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At corrupti ratione officiis, ea ducimus maxime similique amet harum delectus, debitis quod accusamus natus, repellat a error dignissimos id voluptatem. Ratione?</p>
 </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      their_name: this.$route.params.name
    }
  },
}



</script>