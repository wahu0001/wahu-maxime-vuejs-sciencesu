<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <div class="card mt-4">
          <div class="card-body">
            <h3 class="card-title">Nos équipes !</h3>
            <div class="card">
              <ul class="list-group list-group-flush text-center">
                <li v-for="group in recipientsGroup" :key="group.id" class="list-group-item">
                  L'équipe {{group.title}} {{group.icon}}
                  <button @click="showGroup(group.id)" type="button" class="btn btn-secondary btn-sm">Voir</button>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {recipientsGroup} from "../assets/js/recipientsGroup.js"

export default {
  name: "Team",
  data() {
    return {
      recipientsGroup
    }
  },
  methods: {
    showGroup(groupId){
      console.log("here");
      this.$router.push({
        name:"Team",
        params:{groupId}
      })
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
