<template>
  <!-- <div>{{ animalList }}</div> -->
  <div>
    <table>
      <tr>
        <th>Sorts</th>
        <th>Names</th>
        <th>Date of Birth</th>
      </tr>
      <tr v-for="animal in animalList" :key="animal">
        <td>{{ animal.sort }}</td>
        <td>{{ animal.name }}</td>
        <td>{{ animal.dateOfBirth }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      animalList: [
        {
          sort: "dog",
          name: "lesi",
          dateOfBirth: "12.02.1987"
        },
        {
          sort: "cat",
          name: "Garfild",
          dateOfBirth: "12.02.1997"
        },
        {
          sort: "parrot",
          name: "gggg",
          dateOfBirth: "12.02.2007"
        },
        {
          sort: "pig",
          name: "oink",
          dateOfBirth: "12.02.1945"
        },
        {
          sort: "hamster",
          name: "leopoold",
          dateOfBirth: "12.02.2003"
        }
      ]
    };
  }
};
</script>

<style>
</style>
