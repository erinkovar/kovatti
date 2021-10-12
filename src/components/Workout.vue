<template>
    <h3>{{workout.day}}</h3>
    <div>{{workout.description}}</div>
</template>

<script>
export default {
    name: 'Workout',
    props: {
        workout: Object,
    },
}
</script>