<template>
  <div class="dashborad">
    <h1 class="subheading grey--text"> Dashborad </h1>

    <v-content>
        <v-container class="my-3">
          <v-row class="mb-3 ml-2">
            <v-btn small plain
            @click="sortBy('title')">
              <v-icon dark class="mr-4">sort</v-icon>
              <span> by project name </span>
            </v-btn>
            <v-btn small plain
            @click="sortBy('person')">
              <v-icon dark class="mr-4">people_outline</v-icon>
              <span> by person </span>
            </v-btn>
          </v-row>
          

          <v-card class="ma-5 blue lighten-5"
           v-for="project in projects" :key="project.title">
            <v-row no-gutters :class="`pa-3 project ${project.state}`">
              <v-col cols="12" md="5">
                <div class="caption grey--text">Project Title</div>
                <div>{{project.title}}</div>
              </v-col>
              <v-col cols="4" md="2" sm="4">
                <div class="caption grey--text">Person</div>
                <div>{{project.person}}</div>
              </v-col>
              <v-col cols="8" md="2" sm="4">
                <div class="caption grey--text">Due</div>
                <div>{{project.date}}</div>
              </v-col>
              <v-col cols="4" md="2" sm="4">
                <div class="caption grey--text">State</div>
                <div :class="`${project.state} state`">{{project.state}}</div>
              </v-col>
            </v-row>
            <v-divider>
            </v-divider>
          </v-card>

          
        </v-container>
    </v-content>
  </div>
</template>

<script>
  

  export default {
    data(){
      return {
        projects:[
          {title :'MS Azure를 이용한 강우량 예측', person:'Cloud Team', date:'2020/9/1 ~ 2020/12/22',state:'Complete'},
          {title :'Python 기초 데이터 분석', person:'STH', date:'2021/9/1 ~ 2021/11/17', state:'Complete'},
          {title :'포트폴리오 제작', person:'201695050 STH', date:'2021/9/1 ~', state:'OnGoing'},
          {title :'업비트 API를 이용한 가상화폐 등락예측', person:'STH', date:'2021/12/2', state:'Complete'},
          {title :'웹 기본 기능을 가지고 있는 개인 사이트 제작', person:'201695050 STH', date:'2022/1', state:'Begin'},
          
        ]
      }
    },
    methods : {
      sortBy(prop){
        this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
      }
    }
  }
</script>

<style>
  .project.Complete{
    border-left: 5px solid greenyellow;
  }
  .project.OnGoing{
    border-left: 5px solid orange;
  }
  .state.Complete{
    color: #3cd;
  }
  .state.OnGoing{
    color: orange;
  }
  .state.Begin{
    color: grey;
  }

  
</style>