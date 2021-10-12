<template>
<Button text="Add Workout" color="green" />
    <div class="card" :key="workout.id" v-for="workout in workouts">
        <Workout :day="FRIDAY" :description="BLAH" />
        
        <p>Deadlift</p>
        <p>For Time</p>
        <p>30 Deadlifts</p>
        <h4>METCON</h4>
        <p>
            30/25 calorie Assault Bike<br>
            15 Power Snatches<br>
            30 Abmat situps<br>
        </p>
    </div>
</template>

<script>
import Button from '../components/Button.vue';
import Workout from '../components/Workout.vue';

export default {
    name: "Workouts",
    components: {
        Button,
        Workout,
    },
    props: {
        workouts: Array,
    }
}
</script>

<style scoped>
.card {
    box-shadow: 0px 4px 20px #B6BFCA;
    padding: 20px;
}
</style>