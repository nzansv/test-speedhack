<script>
import Header from '@/components/Header.vue'
import Courses from '@/components/Courses.vue'
import HomeTasks from '@/components/HomeTasks.vue'
import Announcement from '@/components/Announcement.vue'

export default {
  name: "HomeView",
  components: {
    Courses, HomeTasks, Announcement, Header
  }
}
</script>

<template>
  <main>
    <div class="dashboard">
      <Header></Header>
      <div class="dash-content">
        <Courses/>
        <HomeTasks/>
        <Announcement></Announcement>
      </div>
    </div>
  </main>
</template>

<style scoped>
  .dashboard{
    position: relative;
    min-height: 100vh;
    left: 280px;
    width: calc(100% - 280px);
    padding: 2rem 3rem;
  }
  .dash-content{
    padding-top: 2rem;
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
</style>