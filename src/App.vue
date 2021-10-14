<template>
  <div id="app">
    <!-- Aufgabe 1 und Pro Aufgabe -->

    <!-- <div style="display:flex">
      <Sheet bg-color="#3498db" color="white" width="250" height="300">
        <h3>Memo to myself</h3>
        <p>Always prepare for PLFs in time!</p>
        <img src="info.svg" width="80px" />
      </Sheet>
      <Sheet bg-color="#8e44ad" color="yellow" width="400" height="300">
        <p>INSY, SEW and Webtechnologies are our favorite subjects!</p>
        <span style="font-style: italic"
          >Starkschwitz Fiedler, Jan Schreck</span
        >
        <p>Wish is was there!</p>
        <span style="font-style: italic">E. Wahn</span>
      </Sheet>
    </div> -->

    <!-- Aufgabe 2 -->
    <!-- Die Reihenfolge spielt keine Rolle !! -->

    <!-- Aufgabe 3 -->
    <DataTable :desserts="desserts" :headers="headers">
      <template v-slot:header>
        <h2>Watch What You Eat!</h2>
      </template>
      <template v-slot:footer> Created 2021 by Robert Baumgartner </template>
      <template v-slot:bodyr>
        <tr class="last-row">
          <td>Total</td>
          <td>{{ totalCalories }}</td>
          <td>{{ totalFat }}</td>
          <td>{{ totalCarbs }}</td>
          <td>{{ totalProtein }}</td>
          <td></td>
        </tr>
      </template>
    </DataTable>
  </div>
</template>
<script>
// import Sheet from './components/Sheet';
// import AppLayout from './components/AppLayout';
// import AppButton from './components/AppButton';
import DataTable from '@/components/DataTable.vue';

export default {
  name: 'App',
  data() {
    return {
      headers: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Calories', value: 'calories' },
        { text: 'Fat (g)', value: 'fat' },
        { text: 'Carbs (g)', value: 'carbs' },
        { text: 'Protein (g)', value: 'protein' },
        { text: 'Iron (%)', value: 'iron' },
      ],
      desserts: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: '1%',
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: '1%',
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: '7%',
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: '8%',
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: '16%',
        },
      ],
    };
  },

  components: {
    // Sheet,
    // AppLayout,
    // AppButton,
    DataTable,
  },
  computed: {
    totalCalories() {
      return this.desserts
        .map((el) => el.calories)
        .reduce((prev, curr) => prev + curr);
    },
    totalFat() {
      return this.desserts
        .map((el) => el.fat)
        .reduce((prev, curr) => prev + curr);
    },
    totalCarbs() {
      return this.desserts
        .map((el) => el.carbs)
        .reduce((prev, curr) => prev + curr);
    },
    totalProtein() {
      return this.desserts
        .map((el) => el.protein)
        .reduce((prev, curr) => prev + curr);
    },
  },
};
</script>

<style>
.last-row{
  font-weight: bold;

}
</style>
