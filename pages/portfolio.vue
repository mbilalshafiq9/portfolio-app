<template>
  <article class="portfolio active" data-page="portfolio">

    <header>
      <h2 class="h2 article-title">Portfolio</h2>
    </header>

    <section class="projects">

      <ul class="filter-list">

        <li class="filter-item">
          <button class="active" data-filter-btn>All</button>
        </li>
      </ul>

      <div class="filter-select-box">
        <select name="" id="" class="filter-select">
          <option value="">Select Category</option>
          <option value="All">All</option>
          <option value="Web Development">Web Development</option>
        </select>
      </div>

      <ul class="project-list">
        <SkeletonLoader v-if="pending" :blocks="10"/> 
        <li class="project-item  active" v-else-if="projects" v-for="(item, index) in projects.data" :key="item.id" > 
          <a   style="cursor:pointer" @click="showModalFun(item.id)">

            <figure class="project-img">
              <div class="project-item-icon-box">
                <ion-icon name="eye-outline"></ion-icon>
              </div>
              <img :src="item.image" alt="Project Title" class="skeleton-loader__line"  loading="lazy">
            </figure>

            <h3 class="project-title">{{ item.title }}</h3>

            <p class="project-category">{{ item.short_desc }}</p>

          </a>
        </li>

      </ul>
    </section>
    
    <Modal  v-if="showModal" @close="handleClose" :projectId="projectId" />

  </article>
</template>
  

<script setup lang="ts">
import Modal from '~/components/modal.vue';
const config = useRuntimeConfig();
const apiBaseUrl = config.public.apiBaseUrl;

const showModal = ref(false);
const projectId = ref(0);

interface Project {
  id: number;
  title: string;
  short_desc: string;
  image:string;
  // Add other fields as necessary
}
interface ApiResponse {
  status: boolean;
  message: string;
  data: Project[];
}
console.log(process.env.APP_NAME);

let {pending, data: projects } = useLazyFetch<ApiResponse>(apiBaseUrl+"/projects.php");

const showModalFun = (id:number) => {
  showModal.value = true;
  projectId.value=id;
};

const handleClose = () => {
      showModal.value = false;
};

</script>



<style scoped>
.skeleton-loader__line {
  background: linear-gradient(90deg, rgba(255, 255, 255, 0.2) 25%, rgba(255, 255, 255, 0.1) 50%, rgba(255, 255, 255, 0.2) 75%);
  background-size: 200% 100%;
  animation: shine 1.5s infinite;
  margin-bottom: 8px;
  border-radius: 4px;
}
@keyframes shine {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}
</style>