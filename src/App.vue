<template>
   <div style="margin:10% 40%; width:250px;">
      <div id="dropdownlist_country">
        <ejs-dropdownlist :dataSource='dataItem' :fields='dataFields' 
        placeholder='Select a country' :change='onCountryChange'
        ref='dropdownInstance'>
        </ejs-dropdownlist>
      <div id="dropdownlist_state" style="padding-top:20px;">
        <ejs-dropdownlist :dataSource='stateDataItem' :fields='stateDataFields'
        placeholder='Select a state' :enabled='enableDropdown'
        :query='childDataQuery'>
        </ejs-dropdownlist>
      </div>
      </div>
    </div>
</template>

<script>
import Vue from 'vue';
import { DropDownListPlugin } from "@syncfusion/ej2-vue-dropdowns";
import { Query } from "@syncfusion/ej2-data";
Vue.use(DropDownListPlugin);

export default Vue.extend({
  data: function() {
    return {
      enableDropdown: false,
      childDataQuery: null,
      dataItem: [
        { CountryName: 'United States', CountryId: '1' },
        { CountryName: 'Australia', CountryId: '2' }
      ],
      dataFields: { text: 'CountryName', value: 'CountryId' },
      stateDataItem: [
        { StateName: 'New York', StateId: '101', CountryId: '1' },
        { StateName: 'Virginia ', StateId: '102', CountryId: '1' },
        { StateName: 'Tasmania ', StateId: '105', CountryId: '2' }
      ],
      stateDataFields: { text: 'StateName', value: 'StateId'},
    };
  },
  methods: {
    onCountryChange: function(args) {
      this.enableDropdown = true;
      this.childDataQuery = new Query().where('CountryId', 'equal', args.value);
    }
  }
});
</script>

<style>
@import url(https://cdn.syncfusion.com/ej2/material.css);
</style>