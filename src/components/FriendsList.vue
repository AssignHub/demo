<template>
  <v-card>
    <v-card-title class="pb-0">My Friends</v-card-title>
    <v-list dense>
      <v-list-item v-for="(f, i) in friends" :key="i">
        <v-tooltip right>
          <template v-slot:activator="{ on, attrs }">
            <v-list-item-content
              v-bind="attrs" 
              v-on="on"
              style="display: block; overflow: hidden; white-space: nowrap; text-overflow: ellipsis;"
            >
              {{ f.firstName }} {{ f.lastName }}
            </v-list-item-content>
          </template>
          <span>{{ f.firstName }} {{ f.lastName }}</span>
        </v-tooltip>
        <v-list-item-icon>
          <img :src="emojis[f.emojiIndex]" style="height: 30px;">
        </v-list-item-icon>
      </v-list-item>
    </v-list>
    <v-btn
      text
      block
      class="grey lighten-2"
    >+ Add Friend</v-btn>
  </v-card>
</template>

<style scoped>
  .v-btn {
    border-top-left-radius: 0;
    border-top-right-radius: 0;
  }
</style>

<script>
export default {
  name: 'FriendsList',

  props: {
    friends: { type: Array, required: true },
    emojis: { type: Array, required: true },
  },
}
</script>