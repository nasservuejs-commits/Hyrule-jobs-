<script setup lang="ts">
import type Job from '@/types/Job.ts'
import type OrderTerm from '@/types/OrderTerm';
const { jobs, order } = defineProps<{ jobs: Job[], order: OrderTerm }>();
</script>
<template>
  <div class="job-list">
    <p>Order by {{ order }}</p>
    <TransitionGroup name="job-list" class="list" tag="ul">
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <img src="../assets/rupee.svg" alt="rupee icon">
          <p>{{ job.salary }} rupees</p>
        </div>
        <div class="description">
          <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Mollitia, nemo animi. Asperiores odit blanditiis cupiditate porro itaque fugit non voluptates quam doloremque esse dolores beatae, veniam hic aperiam repellendus enim.</p>
        </div>
      </li>
    </TransitionGroup>
  </div>
</template> 

<style scoped>
 .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
  .job-list-move {
    transition: transform 0.5s ease;
  }
</style>