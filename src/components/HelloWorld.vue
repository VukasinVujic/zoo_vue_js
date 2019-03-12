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

      <label for="dateOfBirth">Date of Birth</label>
      <input v-model="animal.dateOfBirth" type="text" name="dateOfBirth">
      <br>

      <label for="sektor">sektor</label>
      <select v-model="animal.sektor">
        <option v-for="sektor in nizSektora" :key="sektor">{{sektor }}</option>
      </select>
      <br>
      <br>

      <button type="submit">add animal</button>
    </form>
    <br>
    <table>
      <tr>
        <th>Sorts</th>
        <th>Names</th>
        <th>Date of Birth</th>
        <th>SEktor</th>
      </tr>
      <tr v-for="(animal, index) in animalList" :key="index">
        <td>{{ animal.sort }}</td>
        <td>{{ animal.name }}</td>
        <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'NEpoznato' }}</td>
        <td>{{ animal.sektor ? animal.sektor : "Nema sektor"}}</td>
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
        dateOfBirth: "",
        sektor: ""
      },
      nizSektora: ["ptice", "gmizavci", "sisari", "insekti"]
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
