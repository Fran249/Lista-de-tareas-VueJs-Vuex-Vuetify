<template>
    <v-container grid-list-xl>
        <v-layout row wrap>
            <v-flex md6>
                <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
                   <v-card-text>
                       <v-chip label color="pink" text-color="white">
                           <v-icon>mdi-label</v-icon>
                           {{item.titulo}}
                       </v-chip>
                       <p>
                      {{item.descripcion}}
                       </p>
                       <v-btn color="warning" @click="editar(index)">Editar</v-btn>
                       <v-btn color="error" class="ml-3" @click="eliminarTarea(item.id)">Eliminar</v-btn>
                   </v-card-text>
                </v-card>
                <v-card class="mb-3">
                   <!-- <v-card-text>
                       <v-chip label color="pink" text-color="white">
                           <v-icon>mdi-label</v-icon>
                           Titulo de Tarea #2
                       </v-chip>
                       <p>
                        Lorem ipsum dolor sit amet.
                        Lorem ipsum dolor sit amet.
                        Lorem ipsum dolor sit amet.
                       </p>
                       <v-btn color="warning">Editar</v-btn>
                       <v-btn color="error" class="ml-3">Eliminar</v-btn>
                   </v-card-text> -->
                </v-card>
            </v-flex>

            <v-flex md6 v-if="formAgregar">
                <v-card class="mb-3 pa-3">
                    <v-form @submit.prevent="agregarTarea">
                        <v-text-field label="Titulo de la Tarea" v-model="titulo"></v-text-field>
                        <v-textarea label="Descripcion de Tarea" v-model="descripcion"></v-textarea>
                        <v-btn block color="success" type="submit">Agregar Tarea</v-btn>
                    </v-form>
                </v-card>
            </v-flex>
            <v-flex md6 v-if="!formAgregar">
                <v-card class="mb-3 pa-3">
                    <v-form @submit.prevent="editarTareas">
                        <v-text-field label="Titulo de la Tarea" v-model="titulo"></v-text-field>
                        <v-textarea label="Descripcion de Tarea" v-model="descripcion"></v-textarea>
                        <v-btn block color="warning" type="submit">Editar Tarea</v-btn>
                    </v-form>
                </v-card>
            </v-flex>
        </v-layout>
        <v-snackbar
        v-model="snackbar">
            {{ mensaje }}
            <v-btn
            color="white"
            depressed
            @click="snackbar = false"
            class="ml-5"
            text>
                Cerrar
            </v-btn>
        </v-snackbar>
    </v-container>
</template>

<script>
export default {
    data(){
        return{
            listaTareas:[
                {id: 1, titulo: 'Titulo tarea #1', descripcion: 'Lorem ipsum dolor sit amet.Lorem ipsum dolor sit amet.Lorem ipsum dolor sit amet.'},
                {id: 2, titulo: 'Titulo tarea #2', descripcion: 'Lorem ipsum dolor sit amet.Lorem ipsum dolor sit amet.Lorem ipsum dolor sit amet.'},
            ],
            titulo:'',
            descripcion: '',
            snackbar: false,
            mensaje:'',
            formAgregar: true,
            indexTareas:'',

        }
    },
    methods: {
        agregarTarea(){
            if(this.titulo === '' || this.descripcion === '') {
                this.snackbar = true
                this.mensaje = 'Llena todos los campos'
            }else{
                this.listaTareas.push({
                    id: Date.now(),
                    titulo: this.titulo,
                    descripcion: this.descripcion,
                })
                this.titulo = ''
                this.descripcion = ''
                this.snackbar = true
                this.mensaje = 'Tarea Agregada!'

            }
        },
        eliminarTarea(id){
            this.listaTareas = this.listaTareas.filter(e => e.id !=  id)
        },
        editar(index){
            this.formAgregar = false
            this.titulo = this.listaTareas[index].titulo
            this.descripcion = this.listaTareas[index].descripcion
            this.indexTareas = index
        },
        editarTareas(){
            this.listaTareas[this.indexTareas].titulo = this.titulo
            this.listaTareas[this.indexTareas].descripcion = this.descripcion
            this.formAgregar= true
            this.titulo = ''
            this.descripcion = ''
            this.snackbar = true
            this.mensaje = 'Editaste la Tarea'
        }
    }
}
</script>