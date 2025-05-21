<template>
  <SiteHeader title="KC" />

  <main>
    <div class="container">
      <section class="about">
        <h2>## About Me</h2>
        <UserMeta
          employer="Self"
          :skills="['Kotlin','C#','Python','AWS', 'SQL', 'Vue.js']"
        />
        <p class="intro-text">
          Learn about my code<br/>
          This is my programming site<br/>
          Nice to have you
        </p>
      </section>

      <section class="projects">
        <h2>## Projects</h2>
        <ProjectCard
          v-for="(p,i) in projects"
          :key="i"
          :title="p.title"
          :github="p.github"
          :logo="p.logo"
          :docs="p.docs"
          :desc="p.desc"
          :quote="p.quote"
          :tags="p.tags"
        />
      </section>
    </div>
  </main>

  <!-- <SiteFooter :projects="projects.map(p => p.title)" /> -->
</template>

<script>
import SiteHeader  from './components/Header.vue'
import UserMeta    from './components/UserMetadata.vue'
import ProjectCard from './components/ProjectCard.vue'
import SiteFooter  from './components/Footer.vue'

export default {
  name: 'App',
  components: { SiteHeader, UserMeta, ProjectCard, SiteFooter },
  data() {
    return {
      projects: [
        {
          title: 'Transit App',
          github:'https://github.com/kamclark/transit-tracker/',
          // logo:  'https://placehold.co/200x150',
          logo:  'https://freerangestock.com/sample/123226/train-display-board-.jpg',
          docs:   'https://github.com/kamclark/transit-tracker/blob/main/README.md',
          desc:   'Request proxmity-based updates for nearby train and bus route departures with customizable schedule metrics and severe delay warnings.',
          quote:  'More accurate than the official app!',
          tags:   ['Django','Vue.js','SQL','AWS']
        },
      ]
    }
  }
}
</script>

<style>
@import './style.css'; /* or break into component-scoped CSS */
p:hover {
  /* cursor: pointer */
}
</style>
