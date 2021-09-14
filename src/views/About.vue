<template>

<v-container >

<v-row>

    <v-col cols="12">

        <h2>

            Thirsty? We have hundreds and hundreds of delicious cocktail recipes<br />
            from expert bartenders around the world. No matter if you're looking for a classic cocktail,<br />
            a punch for a party or an original concoction, we have a cocktail recipe for every taste and occasion,<br />
            just a shake, stir or pour away.<br>
            <br /><br />

            Belly up to the bar and get recipes for your favorite drinks. <br />
            Make your own martini, margarita, Bloody Mary—plus all the best cocktail and mocktail recipes.<br /><br />

        </h2>

        <v-dialog v-model="addDialog" o
                  width="800">

            <template v-slot:activator="{ on, attrs }">

                <v-btn color="blue"
                       dark
                       v-bind="attrs"
                       v-on="on">

                    New Cocktail
                </v-btn>

            </template>

            <v-card>

                <v-card-title class="text-h5 blue lighten-2">
                    New Cocktail

                </v-card-title>

                <v-card-text>

                    <Form></Form>

                </v-card-text>

                <v-divider></v-divider>
                <v-card-actions>

                    <v-spacer></v-spacer>

                    <v-btn color="primary"
                           text
                           @click="addDialog = false; successAlert=true;">
                        Submit
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>
    </v-col>
    </v-row>

    <v-row>
      <v-col cols="12">
        <v-alert type="success" v-model="successAlert" dismissible>
      Recipe added!
      </v-alert>
      </v-col>
    </v-row>
   </v-container>
</template>

<script>

import Form from "../components/Form.vue";

export default {
  components:{Form},
      data(){
        return{
          addDialog: false,
          successAlert: false 
        }
      }
    
  }
</script>

<style scoped>
h2 {text-align: center;}
</style>

