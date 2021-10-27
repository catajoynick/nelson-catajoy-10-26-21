<template>
  <v-container>
    <v-form>
      <v-text-field
        v-model="firstName"
        label="First Name"
        :rules="firstNameRule"
        required
      ></v-text-field>
      <v-text-field
        v-model="middleName"
        label="Middle Name"
        :rules="middleNameRule"
        required
      ></v-text-field>
      <v-text-field
        v-model="lastName"
        label="Last Name"
        :rules="lastNameRule"
        required
      ></v-text-field>
      <v-text-field v-model="age" label="Age" required></v-text-field>
    </v-form>

    <v-btn>Submit</v-btn>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      firstName: "",
      firstNameRule: [v => !!v || "Enter a firstname"],
      middleName: "",
      middleNameRule: [v => !!v || "Enter a middlename"],
      lastName: "",
      lastNameRule: [v => !!v || "Enter a lastname"]
    };
  }
};
</script>

<style></style>
