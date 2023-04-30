<template>
  <div class="container">
    <h1 class="header">Social Media</h1>

    <div class="projects">
      <div class="project-card" v-for="(project, index) in projects" :key="index">
        <img :src="'https://picsum.photos/seed/' + index + '/200'" alt="">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="links">
          <a :href="project.liveLink" target="_blank">Live</a>
          <a :href="project.codeLink" target="_blank">Code</a>
        </div>
        <div class="hover-info">
          <p>Hover over card for more info</p>
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

import { Client, Databases, ID } from "appwrite";
const client = new Client();
    client.setEndpoint('http://127.0.0.1/v1')
    client.setProject('644db0bebd03c9964158');

const databases = new Databases(client);


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
    const promise = databases.createDocument(
    '644db67fe5159ca07521',
    '644db9ec37abb6eff869',
    ID.unique(),
this.newProject
);
console.log ( "HELP ME");
promise.then(function (response) {
    console.log(response);
}, function (error) {
    console.log(error);
});
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
  margin-bottom: 80px;
  color: green;
}
.projects{
  margin-top: 70px; 
}
.project-card {
  margin-bottom: 20px; /* changed from 20px */
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
