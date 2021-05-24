<template>
  <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex xs12 sm3>
          <v-card>
            <v-img src="https://blog.desafiolatam.com/wp-content/uploads/2020/11/JS.png">
            </v-img>
            <v-card-title>
              Javascript
            </v-card-title>
              <v-card-text>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa ullam facere ducimus soluta reprehenderit officia natus saepe, inventore aut error exercitationem vel sed voluptates repudiandae quam ex consequatur! Quibusdam, accusamus?</p>
              </v-card-text>
              <v-card-actions>
                <v-btn color="info" depressed @click="dialog = true">Accion</v-btn>
              </v-card-actions>
            
          </v-card>
        </v-flex>
         <v-flex xs12 sm3>
          <v-card>
            <v-img src="https://blog.desafiolatam.com/wp-content/uploads/2020/11/JS.png">
              <v-container fill-height>
                <v-layout>
                  <v-flex>
                    <span class="headline white--text">
                      Lorem, ipsum dolor.
                    </span>
                  </v-flex>
                </v-layout>
              </v-container>
            </v-img>
            <v-card-title>
              Javascript
            </v-card-title>
              <v-card-text>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa ullam facere ducimus soluta reprehenderit officia natus saepe, inventore aut error exercitationem vel sed voluptates repudiandae quam ex consequatur! Quibusdam, accusamus?</p>
              </v-card-text>
              <v-card-actions>
                <v-btn color="info" depressed>Accion</v-btn>
              </v-card-actions>
            
          </v-card>
        </v-flex>
      </v-layout>
      <!--dialog-->

          <v-dialog v-model="dialog" width="500" persistent>
            <v-card>
              <v-card-title>Titulo</v-card-title>
              <v-card-text>
                Lorem ipsum dolor sit. 
                Lorem ipsum dolor sit.
              </v-card-text>
              <v-divider></v-divider>
              <v-card-actions>
                <v-btn color="red" @click="dialog = false">Cerrar</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>

      <!--dialog-->

      
  </v-container>
</template>

<script>

  export default {
      data(){
        return{
          dialog: false
        }
      }
  }
</script>
