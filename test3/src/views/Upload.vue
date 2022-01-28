<template>
    <div class="Upload">
        <h1> Upload </h1>
                
            <div style="display :flex">
                <v-card 
                v-for="project in projects" :key="project.title"
                class="mx-auto ma-3"
                max-width="400"
                
                >
                    <v-img
                    class="white--text align-end"
                    height="200px"
                    img :src="project.image"
                    >
                    <v-card-title>{{title}}</v-card-title>
                    </v-img>

                    <v-card-subtitle class="pb-0">
                    {{project.content}}
                    </v-card-subtitle>

                    <v-card-text class="text--primary">
                        <div>{{project.person}}</div>

                        <div>{{projects.due}}</div>
                    </v-card-text>

                    <v-card-actions>
                    
                      <v-btn
                         color="orange"
                          text
                      >
                          Let's Go!
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            projects:[
          {title :'MS Azure를 이용한 강우량 예측', person:'Cloud Team', date:'2020/9/1 ~ 2020/12/22', state:'Complete',content:'Azure 플랫폼과 R언어를 이용한 강우량 예측',image:"/Azure machinlearn.PNG"},
          {title :'포트폴리오 제작', person:'STH', date:'2021/9/1 ~', state:'OnGoing',content:'Vue와 Vuetify를 이용한 과거 제작물 포폴제작',image:"/포폴.png"},
          {title :'업비트 API를 이용한 가상화폐 등락예측', person:'STH', date:'2022/1', state:'Begin',content:'Python의 skitlearn의 ARMR 알고리즘을 이용하여 원하는 가상화폐 가격을 예측',image:"/ARIMA.png"},
        ]
        }
    }
}
</script>