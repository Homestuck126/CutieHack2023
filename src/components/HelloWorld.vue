



<template>

    <h1 class="header">TINDER 2.0</h1>
    
  <div class="container">
    <div class="projects">
      <div class="project-card" v-for="(project, index) in projects" :key="index">
        <img :src="'https://picsum.photos/seed/' + index + '/200'" alt="">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="links">
          <a :href="project.liveLink" target="_blank">Live</a>
          <a :href="project.codeLink" target="_blank">Code</a>
        </div>
        
      </div>
    </div>

    <div class="form-container">
      <h2>Add a New Project</h2>
      <form>
        <label for="title">Title</label>
        <input type="text" id="title" v-model="newProject.title">

        <label for="description">Description</label>
        <textarea id="description" v-model="newProject.description"></textarea>

        <label for="live-link">Live Link</label>
        <input type="text" id="live-link" v-model="newProject.liveLink">

        <label for="code-link">Code Link</label>
        <input type="text" id="code-link" v-model="newProject.codeLink">

        <button type="button" @click="addProject()">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
 
  data() {
    return {
      projects: [
        {
          title: "My Project 1",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          liveLink: "https://example.com",
          codeLink: "https://github.com"
        },
        {
          title: "My Project 2",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          liveLink: "https://example.com",
          codeLink: "https://github.com"
        },
        {
          title: "My Project 3",
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          liveLink: "https://example.com",
          codeLink: "https://github.com"
        }
      ],
      newProject: {
        title: "",
        description: "",
        liveLink: "",
        codeLink: ""
      }
    }
  },
  methods: {
    addProject() {
      this.projects.push(this.newProject);
      this.newProject = {
        title: "",
        description: "",
        liveLink: "",
        codeLink: ""
      };
    }
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
  margin-bottom: 90px;
  color: green;
  font-size: 70px;
}
.projects{
 display: flex;
  flex-wrap: wrap;
  justify-content: space-between; /* add space between the columns */
  margin-top: 100px; 
  width: 200%;
}
.project-card {
  width: calc(33.33% - 15px); /* adjust the width to fit three cards per row */
  margin-bottom: 20px;
  border: 4px solid orange;
  border-radius: 15px;
  padding: 7px;
  position: relative;
  
}

.project-card img {
  width: 100%;
  height: auto;
  margin-bottom: 10px;
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

button {

  background-color: #ADD8E6;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #87CEFA;
}


h1 {
  font-weight: 600;
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
  height: 90%;
  background-color: #ADD8E6;
  z-index: -1;
}
ul {
  font-size: 1.2rem;
  position: fixed;
  top: 0;
  left: 0;
  
}
.form-container {
  position: fixed;
  top: 0;
  right: 0%;
  width: 30%;
  height: 10%;
  background-color: black;
  border: 1px solid black;
  padding: 1px;
}
label {
  font-size: 15px

}

input {
padding: 2px;

}
textarea{
  padding: 1px;
}
</style>

