
<template>
  <div>
    <h2>Handsontable Basic Example (100x10)</h2>
    <p>
      Head to
      <a href="https://handsontable.com" target="_blank">handsontable.com</a> to learn more about Handsontable.
    </p>
    <div id="example"></div>
  </div>
</template>

<script>
import Handsontable from 'handsontable'



export default {
  name: 'grid',
  data() {
    return {
      tableData: {

      }
    }
  },
  mounted() {
    this.populateHot();
  },
  methods: {
    populateHot: function () {
      var data = function () {
        return Handsontable.helper.createSpreadsheetData(100, 10);
      };
      console.log(data());

      var container = document.getElementById('example');
      var hot = new Handsontable(container, {
        data: data(),
        minSpareCols: 1,
        minSpareRows: 1,
        rowHeaders: true,
        colHeaders: true,
        contextMenu: true
      });
    }
  }
}
</script>
<style>
@import '../assets/handsontable/handsontable.full.min.css';
@import '../assets/handsontable/main.css';
</style>


