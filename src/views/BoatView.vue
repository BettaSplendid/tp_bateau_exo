<template>
  <div>
    <h1>Here be the form, yarr</h1>
    <button @click="Logs()">Logs</button>
    <div>
      <form @submit.prevent>
        <div>
          <label for="nom_pro">Nom du proprio: </label>
          <input
            v-model="boat_owner_name"
            type="text"
            name="nom_pro"
            id="nom_pro"
          />
        </div>
        <div>
          <label for="nom_bat">Nom du bateau: </label>
          <input v-model="boat_name" type="text" name="nom_bat" id="nom_bat" />
        </div>
        <div>
          <label for="taille">Taille du Bateau: </label>
          <input v-model="boat_size" type="text" name="taille" id="taille" />
        </div>
        <div>
          <label for="">Prix: </label>
          <input
            v-model.number="boat_price"
            type="number"
            name="prix"
            id="prix"
            min="0"
            step="1"
          />
        </div>
        <input type="submit" value="submit" />
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { useBoatStore } from "../stores/boat_store";

const StoreStoreStore = useBoatStore();
const boat_owner_name = ref();
const boat_name = ref();
const boat_size = ref();
const boat_price = ref();

function Logs() {
  console.log("Logs");
  console.log(boat_owner_name.value);
  console.log(boat_name.value);
  console.log(boat_size.value);
  console.log(boat_price.value);
  // console.log(taille);
}

function SaveDataStore() {
  console.log("SaveDataStore");
  console.log(boat_owner_name.value);
  console.log(boat_name.value);
  console.log(boat_size.value);
  console.log(boat_price.value);

  if (
    !boat_owner_name.value ||
    !boat_name.value ||
    !boat_size.value ||
    !boat_price.value
  ) {
    alert("Veuillez remplir tous les champs");
  }


}
</script>
