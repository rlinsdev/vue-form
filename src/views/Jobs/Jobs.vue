<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <h2 @click="jobDetail(job.id)" >{{job.title}}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs:[
        {title: 'Ninja UX Designer', id:'1', details: 'Lorem'},
        {title: 'Ninja Web Developer', id:'2', details: 'Lorem'},
        {title: 'Ninja Vue Developer', id:'3', details: 'Lorem'}
      ]
    }
  },
  methods:{
    jobDetail(id){
      this.$router.push({ name: 'JobsDetails', params: { id: id } })
    }
  }
}
</script>

<style>

</style>