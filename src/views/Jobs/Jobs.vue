<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id" class="job">
    <router-link :to="{name: 'JobsDetails', params:{id: job.id}}">
      <h2>{{job.title}}</h2>
    </router-link>
    <!-- <h2 @click="jobDetail(job.id)" >{{job.title}}</h2> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      //jobs:[]
      jobs:[ ]
    }
  },
  monted() {
    fetch('http://localhost:3000/jobs')
      .then(res=>res.json())
      .then(data => this.jobs = data)
      .catch(err => console.log(err.message))
  }
  // methods:{
  //   jobDetail(id){
  //     this.$router.push({ name: 'JobsDetails', params: { id: id } })
  //   }
  // }
}
</script>

<style>
.job h2{
  background: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color:#444
}

.job h2:hover {
  background: #ddd;
}

.job a {
  text-decoration: none;
}
</style>