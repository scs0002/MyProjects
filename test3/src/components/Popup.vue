/* eslint-disable prettier/prettier */
<template>
  <v-dialog max-width="600px">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="grey lightne 4" dark v-bind="attrs" v-on="on">
        Add New Project
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        <span class="text-h5"> Add a New Project</span>
      </v-card-title>

      <v-card-text>
        <v-form class="px-3">
          <v-text-field label="Title" v-model="title" prepend-icon="folder">
          </v-text-field>
          <v-textarea label="Info" v-model="content" prepend-icon="edit">
          </v-textarea>
          <v-menu
            v-model="menu2"
            :close-on-content-click="false"
            :nudge-right="40"
            transition="scale-transition"
            offset-y
            min-width="auto"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                v-model="date"
                label="Picker without buttons"
                prepend-icon="mdi-calendar"
                readonly
                v-bind="attrs"
                v-on="on"
              ></v-text-field>
            </template>
            <v-date-picker
              v-model="date"
              @input="menu2 = false"
            ></v-date-picker>
          </v-menu>
        </v-form>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn class="success mx-0 mt-3" @click="submit"> Add </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
import { collection, addDoc } from "firebase/firestore";
import db from "../fb"

export default {
  data() {
    return {
      title: "",
      contents: "",
      date: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10),
      menu2: false,
    };
  },
  methods: {
    async submit() {
      console.log(this.title, this.contents, this.date);
      const project = {
        title: this.title,
        contents: this.contents,
        due: this.date,
        person: "STH",
        state: "Ongoing"
      };

      try {
              const docRef = await addDoc(collection(db, "projects"),
               {
                title: project.title,
                contents: project.contents,
                due: project.due,
                person: project.person,
                state: project.state,
                
              });
              console.log("Document written with ID: ", docRef.id);
            } 
        catch (e) {
              console.error("Error adding document: ", e);
            }

    },
  },
};
</script>
