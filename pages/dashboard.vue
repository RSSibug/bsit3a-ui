<template>

  <div>
    <v-card>
      <v-card-title>
        List of Student 
        <v-spacer></v-spacer>
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
        ></v-text-field>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="desserts"
        :search="search"
      >
    
      <template slot="item.actions" slot-scope="{ item }">
        <v-btn color="green">Edit</v-btn>
        <v-btn color="red">Delete</v-btn>
      </template>
    
    </v-data-table>
    </v-card>
  </div>
  </template>
  
  <script>
    export default {
      data () {
        return {
          headers: [
            {
              text: 'No.',
              align: 'start',
              sortable: false,
              value: 'number',
            },
            { text: 'Student Number', value: 'sn' },
            { text: 'Last Name', value: 'ln' },
            { text: 'First Name', value: 'fn' },
            { text: 'Middle Name', value: 'mn' },
            { text: 'Course', value: 'c' },
            { text: '', value: 'actions'}
          ],
          desserts: [
            {
              number  : '1',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
              v:''
            },
            {
              number  : '2',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },
            {
              number  : '3',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },
            {
              number  : '4',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },
            {
              number  : '5',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },
            {
              number  : '6',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },
            {
              number  : '7  ',
              sn: '21-00313',
              ln: 'Sibug',
              fn: 'RS Joland', 
              mn: 'Mercado',
              c: 'BSIT',
            },  
          ],
        }
      },
    }
  </script> 