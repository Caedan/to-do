<template>
  <div class="dashboard">
    <h1>Dashboard</h1>
    <v-container class="my-5">
      
      <v-layout row class="mb-3">

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
            <v-icon left small>folder</v-icon>
            <span class="caption text-lowercase">By task name</span>
          </v-btn>
          <span>Sort tasks by task name</span>
        </v-tooltip>

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
            <v-icon left small>person</v-icon>
            <span class="caption text-lowercase">By person</span>
          </v-btn>
          <span>Sort tasks by person</span>
        </v-tooltip>

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('due')" slot="activator">
            <v-icon left small>date_range</v-icon>
            <span class="caption text-lowercase">By date</span>
          </v-btn>
          <span>Sort tasks by date</span>
        </v-tooltip>
      </v-layout>

      <v-card flat v-for="task in tasks" :key="task.title">
        <v-layout row wrap :class="`pa-3 task ${task.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Task Title</div>
            <div>{{ task.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{ task.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{ task.due }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="right">
              <v-chip small :class="`${task.status} white--text caption my-2`">{{ task.status }}</v-chip>
            </div>
          </v-flex>
        </v-layout>
      </v-card>

    </v-container>
  </div>
  
</template>

<script>
  export default {
    data() {
      return {
        tasks: [
          { title: 'Develop a to-do website', person: 'Tom Neys', due: '15/03/2019', status: 'ongoing'},
          { title: 'Finish network design', person: 'Alberto Vargas Medina', due: '03/03/2019', status: 'complete' },
          { title: 'Database coursework', person: 'Masfik Hossain', due: '06/03/2019', status: 'overdue'}
        ]
      }
    },
    methods: {
      sortBy(prop){
        this.tasks.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
      }
    }
  }
</script>

<style>

  .task.complete {
    border-left: 4px solid green;
  }
  .task.ongoing {
    border-left: 4px solid orange;
  }
  .task.overdue {
    border-left: 4px solid tomato;
  }
  .v-chip.complete {
    background: green;
  }
  .v-chip.ongoing {
    background: orange;
  }
  .v-chip.overdue {
    background: tomato;
  }

</style>

