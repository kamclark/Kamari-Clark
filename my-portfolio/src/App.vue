<template>
  <SiteHeader title="KC" />

  <main>
    <div class="container">
      <section class="about">
        <h2>## About Me</h2>
        <UserMeta
          employer="Self"
          :skills="['Kotlin','TypeScript','Python','AWS']"
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
          github:'https://github.com/…',
          logo:  'https://placehold.co/200x150',
          docs:   '#',
          desc:   'Real Time Transit Tracking App',
          quote:  'Possibly the best app ever…',
          tags:   ['Typescript','Vue.js','SQL','AWS']
        },
      ]
    }
  }
}
</script>

<style>
@import './style.css'; /* or break into component-scoped CSS */
</style>
