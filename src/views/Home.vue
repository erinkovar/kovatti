<template>
  <div class="home">
    <h1>Workouts</h1>
    <Button @click="onClick()" text="Add Workout" color="green" />
    <Workouts :workouts="workouts" />
    <!-- <AddWorkout  /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "@/components/Button.vue";
import Workouts from "@/components/Workouts.vue";
// import AddWorkout from "@/components/AddWorkout.vue";


export default {
  name: "Home",
  components: {
    Button,
    Workouts,
    // AddWorkout,
  },
  props: {
    text: String,
    color: String,
  },
  data() {
    return {
      workouts: [],
    };
  },
  methods: {
    // async addWorkout(workout) {
      
    // },
    onClick() {
      console.log("Click");
    },
  },
  created() {
    this.workouts = [
      {
        id: 1,
        day: 'Monday',
        type: 'warmup',
        description: '100 burpees for time',
      },
      {
        id: 2,
        day: 'Tuesday',
        type: 'gymnastics',
        description: '100 muscleups for time',
      },
      {
        id: 3,
        day: 'Wednesday',
        type: 'structure',
        description: '5x5 Front Squats @80%',
      },
    ]
  },
};
</script>
