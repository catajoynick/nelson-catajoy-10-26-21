<template>
  <v-data-table
    :headers="headers"
    :items="person"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "Date",
          value: "date"
        },
        {
          text: "First Name",
          align: "start",
          sortable: false,
          value: "firstName"
        },
        { text: "Middle Name", value: "middleName" },
        { text: "Last Name", value: "lastName" },
        { text: "Age", value: "age" }
      ],
      person: [
        {
          date: new Date().toDateString(),
          firstName: "Nelson",
          middleName: "Ylanan",
          lastName: "Catajoy",
          age: 24
        }
      ]
    };
  }
};
</script>
