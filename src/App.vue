<template>
  <div>
    <div style="margin:10% 40%; width:250px">

      <!-- ItemTemplate, HeaderTemplate, FooterTemplate Code Snippet -->
      <!-- <ejs-autocomplete :dataSource='dataItem' 
      :fields='dataFields' placeholder='Select a platform'
      :itemTemplate='autocompleteItemTemplate'
      :headerTemplate='autocompleteHeaderTemplate'
      :footerTemplate='autocompleteFooterTemplate' ref='autocompleteinstance'>
      </ejs-autocomplete> -->

      <!-- GroupTemplate Code Snippet -->
      <ejs-autocomplete  
      :dataSource='dataItem' :fields='dataFields' placeholder='Select a name'
      :groupTemplate="autocompleteGroupTemplate">
      </ejs-autocomplete>
      </div>
    </div>
</template>

<script>
import Vue from 'vue';
import { AutoCompletePlugin } from "@syncfusion/ej2-vue-dropdowns";
Vue.use(AutoCompletePlugin);

export default Vue.extend({
  data: function() {
    return {

      // GroupTemplate Code Snippet
      autocompleteGroupTemplate:"<b><i>${Country}</i></b>",
      dataItem: [
        {EmployeeID:1,EmployeeName:"Anne Dodsworth",Country:"USA"},
        {EmployeeID:2,EmployeeName:"Janet Leverling",Country:"USA"},
        {EmployeeID:3,EmployeeName:"Margaret Peacock",Country:"USA"},
        {EmployeeID:4,EmployeeName:"Robert King",Country:"England"},
        {EmployeeID:5,EmployeeName:"Steven Buchanan",Country:"England"}],
      
      dataFields: { value: 'EmployeeName', groupBy: 'Country' }

      // ItemTemplate, HeaderTemplate, FooterTemplate Code Snippet 
      // autocompleteItemTemplate:"<div class='list-wrapper'><span class= '${Image} e-avatar'></span><span class='text'>${Name}</span></div>",
      // autocompleteHeaderTemplate:"<span class='header'><span class='img'>Photo</span><span class='name'>Platform</span></span>",
      // autocompleteFooterTemplate:"<span class='footer'> Total list item: 5</span>",
      // dataItem: [
      //   { Name: "JavaScript", Id: "item1", Image: "javascript" },
      //   { Name: "TypeScript", Id: "item2", Image: "typescript" },
      //   { Name: "Angular", Id: "item3", Image: "angular" },
      //   { Name: "React", Id: "item4", Image: "react" },
      //   { Name: "Vue", Id: "item5", Image: "vue" }   
      // ],
      // dataFields: { text: 'Name', value: 'Id' }
      
    };
  }
  // FooterTemplate Code Snippet for getting total list items count
  // mounted() {
  //   document.getElementsByClassName('e-autocomplete')[0].addEventListener('keyup', () => {
  //     this.onOpen();
  //   })
  // },
  //   methods: {
  //   onOpen: function() {
  //     var count = this.$refs.autocompleteinstance.getItems().length;
  //     var ele = document.getElementsByClassName('footer')[0];
  //     ele.innerHTML =  "Total list item: " + count;
  //   }
  // }
});
</script>


<style>
 @import url(https://cdn.syncfusion.com/ej2/material.css);

/* CSS styles for ItemTemplate, HeaderTemplate, FooterTemplate */

/* .list-wrapper {
    height: inherit;
    position: relative;
    padding: 14px 12px 14px 78px;
}

.list-wrapper .text {
  display: block;
  margin: 0;
  padding-bottom: 3px;
  white-space: normal;
  font-size: 13px;
}

.list-wrapper .e-avatar {
    position: absolute;
    left: 5px;
    background-color: transparent;
    font-size: 22px;
    top: calc(50% - 33px);
}

.typescript {
    background-image: url('https://ej2.syncfusion.com/products/images/list-box/javascript1.svg');
}

.javascript {
    background-image: url('https://ej2.syncfusion.com/products/images/list-box/jses5-1.svg');
}

.angular {
    background-image: url('https://ej2.syncfusion.com/products/images/list-box/angular1.svg');
}

.vue {
  background-image: url('https://ej2.syncfusion.com/products/images/list-box/vue.svg');
}

.react {
  background-image: url('https://ej2.syncfusion.com/products/images/list-box/react.svg');
}


 .header,
.list-wrapper {
    display: table;
    width: 100%;
    margin: auto;
}

.header {
    height: 40px;
    font-size: 15px;
    font-weight: 600;
}

.name,
.img {
    display: table-cell;
    vertical-align: middle;   
}
.name {
  width: 70%;
}

.img {
  width: 30%;
}

.header .name {
    text-indent: 15px;
 }

 .header .img {
    text-indent: 8px;
 }

 .footer {
    text-indent: 1.2em;
    display: block;
    font-size: 15px;
    line-height: 40px;
    border-top: 1px solid #e0e0e0;
} */
</style>