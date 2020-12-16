<template>
  <div class="main">
    <div>
      <div class="row" v-for="row in gridRows">
        <div class="col-md-4" v-for="mg in row">
          <monograph :id="mg.id" :name="mg.name" :symbol="mg.symbol" v-on="$listeners" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Monograph from "~/components/monograph";
export default {
  name: "monographList.vue",
  components: {Monograph},
  data: () => {
    return {

    }
  },
  computed: {
    gridRows() {
      var monographs = [
        {
          id: 1,
          symbol: "Ar",
          name: "Argon",
        },
        {
          id: 2,
          symbol: "N2",
          name: "Nitrogen",
        },
        {
          id: 3,
          symbol: "O2",
          name: "Oxygen",
        },
        {
          id: 4,
          symbol: "COCl2",
          name: "Phosgene",
        },
        {
          id: 5,
          symbol: "He",
          name: "Helium",
        },
        {
          id: 6,
          symbol: "CO",
          name: "Carbon Monoxide",
        },
      ]
      var finalMonographs = [];
      var cols = 3;
      for (var m = 0; m < monographs.length;) {
        var row = [];
        for (var i = 0; i < cols; i++) {
          if (m < monographs.length) {
            row.push(monographs[m]);
            m++;
          }
        }
        finalMonographs.push(row);
      }
      return finalMonographs;
    },
  },
  methods: {

  }
}
</script>

<style scoped>

</style>
