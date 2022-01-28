<template>
    <div class="Project">
        <h1> Project </h1>

        <v-container>
            <v-expansion-panels>
                <v-expansion-panel v-for="project in projects" :key="project.tile">
                    <v-expansion-panel-header>
                        {{project.title}}
                    </v-expansion-panel-header>

                    <v-expansion-panel-content>
                        <div class="font-weight-bold"> due by {{project.date}} </div>
                        <div> {{project.content}} </div>
                    </v-expansion-panel-content>
                </v-expansion-panel>
            </v-expansion-panels>
        </v-container>
    </div>
</template>

<script>
export default {
     
    data(){
      return {
        projects:[
          {title :'MS Azure를 이용한 강우량 예측', person:'Cloud Team', date:'2020/9/1 ~ 2020/12/22', state:'Complete',content:'Azure 플랫폼과 R언어를 이용한 강우량 예측'},
          {title :'Python 기초 데이터 분석', person:'STH', date:'2021/9/1~2021/11/17', state:'Complete',content:'머신러닝을 통한 긍정,부정 댓글 예측'},
          {title :'포트폴리오 제작', person:'201695050 STH', date:'2021/9/1 ~', state:'OnGoing',content:'Vue와 Vuetify를 이용한 과거 제작물 포폴제작'},
          {title :'업비트 API를 이용한 가상화폐 등락예측', person:'1', date:'2022/1', state:'Begin',content:'Python의 skitlearn의 ARMR 알고리즘을 이용하여 원하는 가상화폐 가격을 예측'},
          {title :'웹 기본 기능을 가지고 있는 개인 사이트 제작', person:'201695050 STH', date:'2022/1', state:'Begin',content:'JSP와 JS를 이용하여 기본 기능 제작(ex.로그인기능, 접속기록 확인하기)'},
        ]
      }
    },
}
</script>