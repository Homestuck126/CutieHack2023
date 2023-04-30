<template>
  <div class="app">
  
  <h1 class="header"></h1>
  

  <div class="container">
    <div class="projects">
      <div class="project-card" v-for="(project, index) in projects" :key="index">
        <img :src="'https://picsum.photos/seed/' + index + '/200'" alt="">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="links">
         
          <a :href="project.codeLink" target="_blank">Code</a>
        </div>
        

    </div>
</div>
    <div class="form-container" :class="{ 'slide-down': showForm }">
  <button class="toggle-form" @click="showForm = !showForm">Post</button>
  
      <h2>Add a New Project</h2>
      <form>
        <label for="title">Title</label>
        <input type="text" id="title" v-model="newProject.title">

        <label for="description">Description</label>
        <textarea id="description" v-model="newProject.description"></textarea>

         <label for="image">Image</label>
  <input type="file" id="image" @change="onImageSelected">
  
        <label for="code-link">Code Link</label>
        <input type="text" id="code-link" v-model="newProject.codeLink">
      
        <button type="button" @click="addProject()">Add Project</button>
      </form>
    </div>
  </div>
  </div>
</template>

	
import { Client, Databases, ID } from "appwrite";	
	const client = new Client();
	client.setEndpoint('http://127.0.0.1/v1')
	client.setProject('644db0bebd03c9964158');
	
	const databases = new Databases(client);
<script>
export default {
 
  data() {
    return {
     showForm: false, 
      projects: [
        {
          title: "Monster Hunter RPG",
          description: "This game will be a turn based game based on the hub based game Monster HunterIn which players will be prompt with the option to pick form multiple quest to hunt various monsters.During these hunts the player will be faced 1 on 1 against the monster similiar to encounters in pokemon.From then the player will be returned to the hub where they will be given to option to go on other quest, view completed quest, or simply exited the game.",

          codeLink: "https://github.com/cs100/final-project-final-project-bruh"
        },
        {
          title: "PlayListMaker",
          description: "Make your very own playlist of your favorite music that you can listen to",

          codeLink: "https://github.com/stormyy00/Playlist-Makerm"
        },
        {
          title: "PROJECTGRAM",
          description: "A place where youc an create your own porfilio to share with recruiter or just your",

          codeLink: "https://github.com"
        }
      ],
      newProject: {
        title: "",
        description: "",
        image: null,
        codeLink: ""
      }
    }
  },
  methods: {
     onImageSelected(event) {
    const file = event.target.files[0];
    const reader = new FileReader();
    reader.onload = () => {
      this.newProject.image = reader.result;
    }
    reader.readAsDataURL(file);
  },
    addProject() {
      this.projects.push(this.newProject);
      this.newProject = {
        title: "",
        description: "",
        image: null,
        codeLink: ""
      };
      this.showForm = false;
    }
  }
};

</script>

<style>
.container {
position: relative;
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;

}
.app {
  position: top;
}

.header {
  position: fixed;
font-weight: bold;
  text-align: center;
  margin-bottom: 90px;
  color: #42b883;
  font-size: 55px;
  background-color: black;
}
.projects{
 display: flex;
  flex-wrap: wrap;
  justify-content: space-between; /* add space between the columns */
  margin-top: 100px; 
  width: 200%;
}
.project-card {
  width: calc(33.33% - 10px); /* adjust the width to fit three cards per row */
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
.project-card:hover p {
  display: block;
  width: 80%;
  height: 70%;
}
.project-card p {
  margin-bottom: 10px;



  position: absolute;
  top: 40%;
  left: 50%;


  transform: translate(-50%, -50%);
  display: none;
  z-index: 1;
  background-color: rgba(0, 0, 0, 0.8);
  color: #fff;
  padding: 10px;
  border-radius: 5px;

}

.links a {
  display: inline-block;
  margin-right: 10px;
}

.button {
  position: relative;

  background-color: black;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.button::hover {
  background-color: #87CEFA;
}

p {
  font-size: 15px;
  color: black;
}
textarea {
 padding: 10px;
  font-size: 12.5px;
  border-radius: 5px;
  border: 2px solid black;
  outline: none;
  transition: border-color 0.3s ease-in-out; 
}
textarea:focus {
  border-color: blue;
}
h2{
  color: black;
  font-text: bold;
}
label{
  color: black;
}
input[type="text"] {
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  border: 2px solid black;
  outline: none;
  transition: border-color 0.3s ease-in-out;
}

input[type="text"]:focus {
  border-color: blue;
}
h1 {
  font-weight: 600;

  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%
}
h1::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #ADD8E6;
  z-index: -1;
}

.form-container {
  position: fixed;
  top: 70px;
  left: 340px;
  width: 13.5%;
  height: 54.5%;
  padding: 0px;
  background-color: #ADD8E6;
  border-bottom: 5px solid gray;
  border-radius: 5px;
  transform: translateX(-280%);
  transition: transform 0.3s ease;
  z-index: 999;
}

.slide-down {
  transform: translateX(-155.75%);
}

.toggle-form {
  display: block;
  margin: 30;

  left: 100.5%;
  padding: 10px 20px;
  background-color: white;
  color: black;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.toggle-form:hover {
  background-color: #87CEFA;
}



</style>