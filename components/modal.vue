<template>
    <div>
        <div class="modal-container active" id="portfolio-modal">
            <div class="overlay active" style="" id="portfolio-overlay"></div>
            <section class="testimonials-modal block">
              <button class="modal-close-btn" @click="closeModal">
                X
              </button>
             
              <div class="modal-content space-y-3 mt-4" style="width: 100%;" id="modal-content">
                <SkeletonLoader :blocks="2" v-if="pending" /> 
                <div class="data" v-else-if="project">
                  <h4 class="h4 modal-title">{{project.title}} 
                    <a style="display:inline;font-size:14px;color:#FFDB70" :href="project.link" target="_blank">Link</a> 
                  </h4>
                    <p class="text-justify">{{project.short_desc}}</p>
                    <div class="grid-container ">
                        <div class="grid-item " v-for="(image, index) in project.images" :key="index">
                            <a :href="image" target="_blank" >
                              <img :src="image" class="skeleton-loader__line" width="100%">
                            </a> 
                        </div>
                   </div>
                </div>
                  
                
              
              </div>
            </section>
          </div>
    </div>
</template>

<script setup lang="ts">
// Define the emits
const emit = defineEmits<{ (event: 'close'): void }>();

// Define props
interface Props {
  projectId: number;
}

const props = defineProps<Props>();

interface Project {
  id: string;
  title: string;
  short_desc: string;
  images: string[];
  link:string;
}

let {pending, data: project } = useLazyFetch<Project>(`https://imbilalshafiq.com/portfolio-api/projects.php?project=${props.projectId}`);


const closeModal = () => {
      // Emit a custom event 'close' to notify the parent component
    emit('close');
}

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