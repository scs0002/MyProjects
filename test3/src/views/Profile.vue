<template>
    <div class="Profile">
        <h1> Profile </h1>
        <v-container>
            <v-row wrap>
                <v-col cols="12" sm="4" md="3"
                v-for="person in team" :key="person.name">
                    <v-card flat outlined class="text-center ma-3">
                        <v-responsive class="pt-6">
                            <v-avatar size="100">
                                <!-- 이미지 영역 -->
                                <img :src="person.avatar">
                            </v-avatar>
                        </v-responsive>
                        <v-card-text>
                            <div class="subheadding">{{person.name}}</div>
                            <div class="gray--text">{{person.role}}</div>
                            <div>{{person.link}}</div>
                        </v-card-text>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    data(){
        return{
            team : [
                {name :'STH', role:'web Developer, Data Scientist', avatar:'/STH.jpg',link:'https://github.com/scs0002'}

            ]
        }
    }
}
</script>