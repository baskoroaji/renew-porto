<template>
  <div>
    <h2 class="uppercase text-xl font-semibold text-gray-400 mb-4">Works Experience</h2>
  <div class="space-y-5">
  </div>
  <main class="py-10 px-6 max-w-2xl mx-auto">
    <Timeline :items="timeline" />
  </main>
  </div>
</template>

<script setup>
import Timeline from '~/components/App/WorksTimeline.vue'

const {data: works} = await useAsyncData('timeline', 
() => queryContent('/works').find())

const timeline = [
  {
    date: '2025/2 - 2025/7',
    title: 'AI Engineer Trainee At Laskar AI By NVIDIA,Lintasarta, and Dicoding',
    description: 'Selected as one of the national participants for a prestigious AI engineering program supported by NVIDIA, Lintasarta, and Dicoding.',
    tags: ['Trainee', 'Machine Learning', 'Python', 'Data Science', 'Deep Learning']
  },
  {
    date: '2024/7 - 2025/11',
    title: 'Freelance Data Analyst and Software Engineer',
    description: 'Designed and developed a Discord Bot for real-time time series analysis using Python, enhancing performance tracking across competitive sub-communities (improved engagement by over 50%)',
    tags: ['Data Analysis', 'Time Series Analysis', 'Python']
  },
  {
    date: '2023/6 - 2023/8',
    title: 'Frontend Developers Intern At BPTI UHAMKA',
    description: 'Prototyped the redesigned homepage of uhamka.ac.id using React.js and Next.js for improved performance and scalability',
    tags: ['React.js', 'Fullstack', 'Next.js']
  }
]
</script>