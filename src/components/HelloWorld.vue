<template>
  <!-- <div>{{ animalList }}</div> -->
  <div>
    <form @submit.prevent="addAnimal">
      <label for="sort">sort</label>
      <input v-model="animal.sort" type="text" name="sort">
      <br>

      <label for="name">Names</label>
      <input v-model="animal.name" type="text" name="name">
      <br>

      <label for="date">Date of Birth</label>
      <input v-model="animal.date" type="text" name="date">
      <br>

      <button type="submit">add animal</button>
    </form>

    <table>
      <tr>
        <th>Sorts</th>
        <th>Names</th>
        <th>Date of Birth</th>
      </tr>
      <tr v-for="(animal, index) in animalList" :key="index">
        <td>{{ animal.sort }}</td>
        <td>{{ animal.name }}</td>
        <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'NEpoznato' }}</td>
        <td>
          <button @click="removeAnimal(index)">REMOVE</button>
        </td>

        <td>
          <button @click="toTheTop(index)">FLY TO THE TOOOP, YOU GOT TO GET TO THE TOP</button>
        </td>
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
          dateOfBirth: ""
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
      ],
      animal: {
        sort: "",
        name: "",
        dateOfBirth: ""
      }
    };
  },

  methods: {
    removeAnimal(index) {
      this.animalList.splice(index, 1);
    },
    toTheTop(index) {
      const aaaa = this.animalList[index];
      this.animalList.splice(index, 1);
      this.animalList.unshift(aaaa);
    },
    addAnimal(animal) {
      this.animalList.push({ ...this.animal }); // zato sto je objekat
    }
  }
};
</script>

<style>
</style>
