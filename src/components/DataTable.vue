<template>
  <div class="data-table">
    <header><slot name="header"></slot></header>

    <table>
      <thead>
        <tr>
          <th v-for="h of headers" :key="h">{{ h.text }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="d of desserts" :key="d">
          <td>{{ d.name }}</td>
          <td>{{ d.calories }}</td>
          <td>{{ d.fat }}</td>
          <td>{{ d.carbs }}</td>
          <td>{{ d.protein }}</td>
          <td>{{ d.iron }}</td>
        </tr>
        <slot name="bodyr"></slot>
      </tbody>
    </table>

    <footer><slot name="footer"></slot></footer>
  </div>
</template>

<script>
export default {
  props: {
    desserts: {
      type: Array,
    },
    headers: {
      type: Array,
    },
  },
};
</script>

<style scoped>
.data-table {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  margin: 40px;
  border-collapse: collapse;
  font-size: 0.9em;
  font-family: sans-serif;
  min-width: 400px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.data-table td,
th {
  text-align: left;
}
.data-table footer {
  margin: 30px 0 30px 0;
  font-style: italic;
  text-align: center;
}

.data-table header {
  margin: 30px 0 30px 0;
  text-align: center;
}


.data-table thead tr {
  background-color: #009879;
  color: #ffffff;
  text-align: left;
}
.data-table th,
.data-table td {
  padding: 12px 15px;
}
.data-table tbody tr {
  border-bottom: 1px solid #dddddd;
}
.data-table tbody tr:nth-of-type(even) {
  background-color: #f3f3f3;
}
</style>
