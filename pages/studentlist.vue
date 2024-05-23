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
          :items="studentdata"
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
                text: 'Student No',
                align: 'start',
                sortable: false,
                value: 'attributes.student_no',
              },
              { text: 'Last Name', value: 'attributes.last_name' },
              { text: 'First Name', value: 'attributes.first_name' },
              { text: 'Middle Name', value: 'attributes.middle_name' },
              { text: 'Course', value: 'attributes.course' },
              { text: 'Section', value: 'attributes.section' },
            ],
           studentdata:[

           ],
           search:''
          }
        },

        methods:{
          getStudentList() {
            this.$axios.get("http://localhost:1337/api/student-lists")
            .then(response => {
              console.log("Success")
              console.log(response.data.data)
              this.studentdata = response.data.data 
            })

            .catch(error => {
              console.log("Error")
            })
          }

        },

        mounted() {
          console.log("Auto Run")
          this.getStudentList();
        }

      }
    </script> 