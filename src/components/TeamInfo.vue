<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <div class="card mt-4">
          <div class="card-body">
            <h3 class="card-title">Oh la belle équipe de {{currentGroup.titre}}</h3>
            <h5 class="card-title">Composée de {{currentGroup.recipients | length}} membres</h5>
            <Employee v-for="employee in currentGroup.recipients" :key="employee.email" v-bind:employee="employee"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { recipientsGroup } from "../assets/js/recipientsGroup.js";
// import Employee from "./components/Employee";
import Employee from "@/components/Employee";

export default {
  name: "TeamInfo",
  data() {
    return {
      recipientsGroup,
      currentGroup: null,
    };
  },
  components:{
    Employee
  },
  methods: {
    showGroup(groupId) {
      this.router.push({
        name: "Team",
        params: { groupId },
      });
    },
  },
  filters: {
    length(arr) {
      return arr.length;
    },
  },
  created() {
    this.currentGroup = this.recipientsGroup.find(
      (element) => element.id == this.$route.params.groupId
    );
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
