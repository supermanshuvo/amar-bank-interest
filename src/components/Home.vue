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
                v-model="dps_amount"
                type="number"
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
                v-model="annual_interest_rate"
                type="number"
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
                v-model="no_of_months"
                type="number"
                ></v-text-field>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="3">
                <v-subheader>Principal Amount :</v-subheader>
            </v-col>
            <v-col cols="6">
                <v-text-field
                label="Principal Amount"
                :value="total_principal_amount"
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
                label="Interest Amount"
                :value="total_interest_amount"
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
                label="Total Amount"
                :value="total_amount"
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
          dps_amount:0,
          annual_interest_rate:0,
          no_of_months:0
      }
  },
  computed:{
      total_principal_amount(){
          let dps = parseFloat(this.dps_amount);
          let month = parseFloat(this.no_of_months);
          let cal = dps * month;
          let result = cal.toFixed(2);
          return result;
      },
      total_interest_amount(){
            let number = 2400;
            let dps = parseFloat(this.dps_amount);
            let month = parseFloat(this.no_of_months);
            let rate = parseFloat(this.annual_interest_rate);
            let cal = (dps*rate*month*(month+1))/number;
            let result = cal.toFixed(2);
            return result;
      },
      total_amount(){
          let number = 2400;
          let dps = parseFloat(this.dps_amount);
          let month = parseFloat(this.no_of_months);
          let rate = parseFloat(this.annual_interest_rate);
          let mul = dps*month;
          let div = (rate*(month+1))/number;
          let add = 1+parseFloat(div);
          let cal = mul*add;
          let result = cal.toFixed(2);
          return result;
      }
  }
}
</script>


