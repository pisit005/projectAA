<template>
  <v-container>
    <v-form ref="form" @submit.prevent="addData">
      <h1>Tracking Number</h1>
      <br />
      <div class="row md-5">
        <v-text-field
          v-model="address"
          :rules="addressRules"
          label="Tracking Number"
          class="ma-3"
          solo
          required
        ></v-text-field>
      </div>
      <div class="text-center">
        <v-btn color="#F4D03F" class="mr-4" @click="addData">Track</v-btn>
      </div>
    </v-form>
    <br />
    <div>
      <v-stepper v-model="e13" vertical>
        <v-stepper-step step="1" complete> พัสดุเข้าสู่ระบบ </v-stepper-step>
        <v-stepper-content step="1"> </v-stepper-content>

        <v-stepper-step step="1" complete>
          พัสดุถึงศูนย์คัดแยกสินค้า
        </v-stepper-step>
        <v-stepper-content step="1"> </v-stepper-content>

        <v-stepper-step step="1" complete>
          พัสดุออกจากศูนย์คัดแยกสินค้า
        </v-stepper-step>
        <v-stepper-content step="2"> </v-stepper-content>

        <v-stepper-step step="1" complete> พัสดุถึงสาขาปลายทาง </v-stepper-step>
        <v-stepper-content step="1"> </v-stepper-content>

        <v-stepper-content step="3">
          <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
          <v-btn color="primary" @click="e13 = 4"> Continue </v-btn>
          <v-btn text> Cancel </v-btn>
        </v-stepper-content>

        <v-stepper-step step="4"> พัสดุกำลังนำส่ง </v-stepper-step>

        <v-stepper-content step="4">
          <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
          <v-btn color="primary" @click="e13 = 1"> Continue </v-btn>
          <v-btn text> Cancel </v-btn>
        </v-stepper-content>
      </v-stepper>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      e13: 2,
    }
  },
}
</script>

<style></style>
