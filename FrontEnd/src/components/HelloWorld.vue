

<template>

  <div class="container">
    <div class="header">
      <h1>My Personal Projects</h1>
    </div>
    <div class="content">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <img :src="project.image" alt="Project Image">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="links">
          <a :href="project.liveLink" target="_blank">Live Demo</a>
          <a :href="project.codeLink" target="_blank">Source Code</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          title: "My First Project",
          image: "https://placehold.it/300x200",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          liveLink: "https://example.com",
          codeLink: "https://github.com/example/my-first-project"
        },
        {
          id: 2,
          title: "My Second Project",
          image: "https://placehold.it/300x200",
          description: "Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
          liveLink: "https://example.com",
          codeLink: "https://github.com/example/my-second-project"
        }
      ]
    };
  }
};
</script>

<style>
.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 20px;
}

.header {
  text-align: center;
  margin-bottom: 20px;
  color: green;
}

.project-card {
  margin-bottom: 20px;
}

.project-card img {
  width: 100%;
  height: auto;
  margin-bottom: 20px;
}

.project-card h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.project-card p {
  margin-bottom: 10px;
}

.links a {
  display: inline-block;
  margin-right: 10px;
}



h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}
h1::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #ADD8E6;
  z-index: -1;
}
ul {
  font-size: 1.2rem;
  position: fixed;
  top: 0;
  left: 0;
  
}

.greetings h1,
.greetings ul {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
   
  }
}


</style>
