
<template>
  <div>
    <h2>Handsontable Basic Example (100x10)</h2>
    <p>
      Head to
      <a href="https://handsontable.com" target="_blank">handsontable.com</a> to learn more about Handsontable.
    </p>
    <div id="example" ></div>
  </div>
</template>

<script>
import Handsontable from 'handsontable'
import $ from 'jquery'
console.log($)


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
    this.changeCss();
  },
  methods: {
    populateHot: function () {
      var data = function () {
        return Handsontable.helper.createSpreadsheetData(100, 10);
      };
      // console.log(data());

      var container = document.getElementById('example');
      var hot = new Handsontable(container, {
        data: data(),
        minSpareCols: 1,
        minSpareRows: 1,
        rowHeaders: true,
        colHeaders: true,
        contextMenu: true,
        // currentRowClassName:
        fixedRowsTop : 1
      });
    },
    changeCss:function(){
      // $('.handsontable thead th').css('line-height':'30px','color':'#276');
      $('.handsontable thead th .relative').css('color','#276');
      $('.handsontable thead th .relative').css('line-height','50px');
      // $('.handsontable thead th .relative').css('line-height':'10px','color':'red');
      $('.handsontable thead th').addClass('pl');
    }
  }
}
</script>
<style scoped>

@import '../assets/handsontable/handsontable.full.min.css';
/*@import '../assets/handsontable/main.css';*/
/*.handsontable thead th .relative{
  background-color: #276 !important; 
}
.handsontable thead th .relative{
  font-size: 20px;
}
.handsontable thead {
  background-color: #276;
}
.wtBorder {
  background-color: #F00!important;
}
.ht_master tr td {
  background-color: #F00;
}
.ht_master tr > td:nth-of-type(odd) {
  background-color: #f00;
}*/
.handsontable thead th .pl{
  background-color: #276;
  line-height: 50px;
  color:red;
}
</style>


