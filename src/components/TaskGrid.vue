<template>
    <div class="task-grid">
        <TaskCard v-for="task in tasks" :key="task.name"
        :task="task">
        </TaskCard>
    </div>
</template>

<script>
import TaskCard from './TaskCard.vue'

export default {
    components: { TaskCard },
    props: {
        tasks: {  type: Array, required: true}
    }
}
</script>

<style>


</style>