<template>
    <div>
      <v-card>
        <v-card-title>
          Student List
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
                text: 'Student Number',
                align: 'start',
                sortable: false,
                value: 'number',
              },
              { text: 'Last Name', value: 'ln' },
              { text: 'First Name', value: 'fn' },
              { text: 'Middle Name', value: 'mn' },
              { text: 'Course', value: 'c' },
              { text: 'Section', value: 's' },
            ],
           desserts:[

           ],
           search:''
          }
        },
      }
    </script> 