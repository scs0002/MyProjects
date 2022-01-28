<template>
    <nav>
        <v-toolbar dense rounded>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
            <v-toolbar-title>STH</v-toolbar-title>
            
            <v-spacer></v-spacer>

            <v-btn icon>
                <v-icon>mdi-magnify</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>mdi-heart</v-icon>
            </v-btn>
            
        </v-toolbar>
        <v-navigation-drawer 
        v-model="drawer"
        absolute
        bottom
        temporary
        >
            <v-layout column align-center>
                <v-flex class="mt-4">
                    <v-avatar size="100" class="ml-4">
                        <img src="/STH.jpg">
                    </v-avatar>
                    <p class="white --gray subheading mt-3">SEANG TAE HEAN
                    </p>
                </v-flex>
                <v-flex class="mt-4 mb-5">
                    <Popup></Popup>
                </v-flex>
            </v-layout>
            
            <v-list>
                <v-list-item-group
                 v-model="group"
                 active-class="light-blue--text text--darken-4"
                 >
                    <v-list-item v-for="(item, i) in items" :key="i" :to="item.router">
                        <v-list-item-icon>
                            <v-icon v-text="item.icon"> </v-icon>
                        </v-list-item-icon>
                        <v-list-item-content>
                            <v-list-item-title v-text="item.text"> </v-list-item-title>
                        </v-list-item-content>
                        
                    </v-list-item>
                    
                    
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
import Popup from './Popup.vue'
    export default{
  components: { Popup },
        data : () => ({
            drawer : false,
            group : null,
            items :[
                { icon : 'mdi-domain', text : 'Dashborad', router : '/'},
                { icon : 'mdi-pencil', text : 'MyProject',router : '/Project'},
                { icon : 'mdi-delete', text : 'Profile', router : '/Profile'},
                { icon : 'mdi-account', text : 'School', router : '/School'},
                { icon : 'note_add', text : 'Upload', router : '/Upload'}
                
            ]
        }),
        watch: {
            group () {
                this.drawer = false
                }
        },
    }
</script>