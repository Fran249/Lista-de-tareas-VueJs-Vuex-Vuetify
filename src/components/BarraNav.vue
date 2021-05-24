<template>
<div>
    <v-app-bar app class="warning">

        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

        <v-app-bar-title >
            <h3>Vuetify</h3>
        </v-app-bar-title>
    
        <v-spacer></v-spacer>
        
        <v-btn right class="succes">
            Ingreso
        </v-btn>
        <v-btn right class="error">
            Salir
        </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" color="secondary" temporary>
        <v-layout class="mt-5" column align-center>
            <v-flex>
                <v-avatar>
                    <img src="https://scontent.faep9-2.fna.fbcdn.net/v/t1.6435-9/91659064_1100019800369152_6924851139426910208_n.jpg?_nc_cat=106&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=xtK-7tYJ1igAX-PbaQ1&_nc_ht=scontent.faep9-2.fna&oh=7f06af361baeceadd04e7bbac7425b7a&oe=60CE3816" alt="">
                </v-avatar>
            </v-flex>
            <v-flex class="white--text mt-2" headline>
                Francisco Lopez
            </v-flex>
        </v-layout>
        <v-layout column>
            <v-flex mx-3>
                <v-btn color="succes" block :to="{name:'Home'}" >
                    Home 
                </v-btn>
                <v-btn color="succes" class="mt-2" block :to="{name:'tareas-crud'}">
                     Lista de Tareas
                </v-btn>
            </v-flex>
        </v-layout>
    </v-navigation-drawer>
</div>
</template>

<script>
export default {
    name:'barranav',
    data(){
        return {
        drawer: false
        }
    },
}
</script>