<template>
  <main>
    <div class="main-content">
      <section class="about">
        <h2>## About Me</h2>
        <UserData
          currentEmployer="Self"
          :skills="['C#', 'Python', 'Vue.js', 'React.js', 'Kotlin', 'SQL', 'AWS']"
        />
        <p class="intro-text">
          Learn about my code<br />
          This is my programming site<br />
          Nice to have you
        </p>
      </section>

      <section class="projects">
        <h2>## Projects</h2>
        <ProjectCard
          v-for="(p, i) in projects"
          :key="i"
          :title="p.title"
          :github="p.github"
          :thumbnailURL="p.thumbnailURL"
          :docs="p.docs"
          :desc="p.desc"
          :quote="p.quote"
          :quoteAuthor="p.quoteAuthor"
          :tags="p.tags"
        />
      </section>
    </div>
  </main>
</template>

<script>
import UserMetadata from "../components/UserInfoWindow.vue";
import ProjectCard from "../components/ProjectCard.vue";

export default {
  name: "HomeView",
  components: { UserData: UserMetadata, ProjectCard },
  data() {
    return {
      projects: [
        {
          title: "Transit App",
          github: "https://github.com/kamclark/transit-tracker/",
          thumbnailURL: "./trains.jpg",
          logo: "https://freerangestock.com/sample/123226/train-display-board-.jpg",
          docs: "https://github.com/kamclark/transit-tracker/blob/main/README.md",
          desc:
            "Request proxmity-based updates for nearby train and bus route departures with customizable schedule metrics and severe delay warnings.",
          quote: "More accurate than the official app!",
          quoteAuthor: "Satisfied User",
          tags: ["Django", "Vue.js", "Redis", "NoSQL", "AWS"],
        },
      ],
    };
  },
};
</script>

<style>
.main-content {
  max-width: var(--max-width);
  margin: 0 auto; /* center container in middle */
  padding: var(--gutter); /* a little room before main content starts */
}

</style>
