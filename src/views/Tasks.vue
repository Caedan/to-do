<template>
  <div class="tasks">
    <h1>Tasks</h1>
    <v-container class="my-5">
      <v-expansion-panel>
        <v-expansion-panel-content v-for="task in myTasks" :key="task.title">
          <div slot="header">{{ task.title }}</div>
          <v-card>
            <v-card-text class="px-4">
              <div class="font-weight-bold">due by {{ task.due }}</div>
              content
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-container>
  </div>
  
</template>

<script>
  export default {
    data(){
      return {
          tasks:[
          { title: 'Develop a to-do website', person: 'Tom Neys', due: '15/03/2019', status: 'ongoing'},
          { title: 'Finish network design', person: 'Alberto Vargas Medina', due: '03/03/2019', status: 'complete' },
          { title: 'Database coursework', person: 'Masfik Hossain', due: '06/03/2019', status: 'overdue'}
        ]
      }
    },
    computed: {
      myTasks() {
        return this.tasks.filter(task => {
          return task.person === 'Tom Neys'
        })
      }
    }
  }
</script>
