<template>
  <v-container fill-height fluid>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="6">
        <v-list subheader>
          <v-subheader>Recent chat</v-subheader>
          <draggable v-model="items">
            <v-list-item
              v-for="item in items"
              :key="item.title"
            >
              <v-list-item-avatar>
                <v-img :src="item.avatar" />
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title v-text="item.title" />
              </v-list-item-content>

              <v-list-item-icon>
                <v-icon :color="item.active ? 'yellow' : 'grey'">
                  chat_bubble
                </v-icon>
              </v-list-item-icon>
            </v-list-item>
          </draggable>
        </v-list>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  components: { draggable },
  data () {
    return {
      items: [
        { active: true, title: 'Jason Oner', avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg' },
        { active: true, title: 'Ranee Carlson', avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg' },
        { title: 'Cindy Baker', avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg' },
        { title: 'Ali Connors', avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg' }
      ],
      items2: [
        { title: 'Travis Howard', avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg' }
      ]
    }
  }
}
</script>
