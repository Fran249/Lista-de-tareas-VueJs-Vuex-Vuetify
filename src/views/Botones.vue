<template>
    <v-container>
        <v-layout>
            <v-flex>

                <v-btn>
                    Texto
                </v-btn>
                <v-btn color="primary ml-5" >
                    Texto
                </v-btn>
                <v-btn  dark color="blue ml-5">
                    Texto
                </v-btn>
                <v-btn color="secondary" class="ml-5" text>
                    Sin fondo
                </v-btn>
                <v-btn color="warning ml-5" large>
                    Largo
                </v-btn>
                <v-btn color="orange ml-5" small>
                    Chico
                </v-btn>
                <v-btn color="warning" class="ml-5" disabled>
                    Disabled
                </v-btn>
                <v-btn color="blue" class="ml-5" depressed>
                    Depressed
                </v-btn>
                <v-btn  icon depressed class="ml-5">
                    <v-icon color="red">mdi-heart</v-icon>
                </v-btn>
                <v-btn  fab depressed small class="ml-5">
                    <v-icon color="red">mdi-heart</v-icon>
                </v-btn>
                <v-btn  fab depressed large class="ml-5">
                    <v-icon color="red">mdi-heart</v-icon>
                </v-btn>
                <v-btn outlined color="success" class="ml-5" block rounded>
                    Texto
                    <v-icon right>mdi-forum</v-icon>
                </v-btn>

            </v-flex>
        </v-layout>
    </v-container>
</template>


<script>
export default {
    data(){
        return{

        };
    }
};
</script>