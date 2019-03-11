<template>
  <div class="team">
    <h1>Team</h1>
    <v-container class="my-5">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
          <v-card flat class="text-xs-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="grey lighten-2">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn flat color="grey">
                <v-icon small left>message</v-icon>
                <span>MESSAGE</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        team: [
        { name: 'Tom Neys', role: 'Data Scientist', avatar: 'avatar.jpg' },
        { name: 'Alberto Vargas Medina', role: 'Data Analyst', avatar: 'avatar.png' },
        { name: 'Masfik Hossain', role: 'Software Developer', avatar: 'avatar.png' },
        { name: 'Sadia "Ava" Afreen', role: 'Social Media maverick', avatar: 'avatar.png' }
        ]
      }
    }
  }
</script>
