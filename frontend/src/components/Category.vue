<template>
  <b-jumbotron class="p-3">
    <b-row>
      <b-col><h3>{{title}}</h3></b-col>
      <b-col>
        <b-btn pill variant="outline-secondary" @click="addEffort(title)">+ Effort</b-btn>
      </b-col>
    </b-row>
    <div align="left" class="mb-2">
      {{description}}
    </div>

    <Effort v-for="effort in efforts" :key="effort.id"
    :title="effort.name"
    :author="effort.author_id"
    :tasks="effort.tasks"
    />

  </b-jumbotron>
</template>


<script>
import Effort from "./Effort.vue"

/*
import api from "@/plugins/api.js"

function get_effort(effort, callback) {
  api.get(`/effort/${category}`).then(callback)
}
*/

export default {
  components: {
    Effort
  },
  props: {
    title: {
      type: String
    },
    description: {
      type: String,
      default: "This is a category."
    },
    efforts: {
      type: Object
    },
    addEffort: {
      type: Object,
      default: (arg) => console.log(arg)
    }
  }

}

</script>
