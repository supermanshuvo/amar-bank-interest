<template>
  <v-app>
    <Nav />
    <v-container>
        <v-row>
            <v-col cols="3">
                <v-subheader>Starting Date : </v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field value="" slot="activator" label="Starting Date : "></v-text-field>
                <!-- <v-date-picker v-model="date"></v-date-picker> -->
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>DPS Amount</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Amount"
                value="10.00"
                prefix="$"
                outlined
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>Annual Interest Rate: </v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Rate"
                value="10.00"
                prefix="%"
                outlined
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>No. Of Months :</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Months"
                value="10"
                outlined
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>Principal Amount :</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Amount"
                value="10.00"
                prefix="$"
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>Interest Amount :</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Amount"
                value="10.00"
                prefix="$"
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>Total Amount :</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Amount"
                value="10.00"
                prefix="$"
                ></v-text-field>
            </v-col>
        </v-row>
    </v-container>
  </v-app>
</template>

<script>
import Nav from './Nav.vue'

export default {
  name: 'Home',
  components: {
    Nav
  },
  data(){
      return{
          
      }
  }
}
</script>


