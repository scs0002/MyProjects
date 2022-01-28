<template>
    <div class="School">
        <h1> School </h1>
         <v-timeline>
            <v-timeline-item
            v-for="(year, i) in years"
            :key="i"
            :color="year.color"
            small
            >
            <template v-slot:opposite>
                <span
                :class="`headline font-weight-bold ${year.color}--text`"
                v-text="year.year"
                ></span>
            </template>
            <div class="py-4">
                <h2 :class="`headline font-weight-light mb-4 ${year.color}--text`">
                {{year.sname}}
                </h2>
                <div>
                  {{year.ex}}
                </div>
            </div>
            </v-timeline-item>
        </v-timeline>
    </div>
</template>

<script>
  export default {
    data: () => ({
      years: [
        {
          color: 'green',
          year: '2004',
          sname : '구암초등학교',
          ex : '2004년 1년 재학 후 전학'
        },
        {
          color: 'brown',
          year: '2009',
          sname : '양덕초등학교',
          ex : '2005년 부터 2009년 까지 재학 후 졸업'
          
        },
        {
          color: 'green',
          year: '2012',
          sname : '중앙중학교',
          ex : '2010년 중앙중 학교 입학 후 2012년 졸업'
        },
        {
          color: 'brown',
          year: '2015',
          sname : '창신고등학교',
          ex : '2013 창신고등학교 입학후 2015년 창신고 졸업'
        },
        {
          color: 'blue',
          year: '2016',
          sname : '신라대학교',
          ex : '2016년 신라대학교 입학 후 2022년 2월 졸업 예정'
        }
      ],
    }),
  }
</script>