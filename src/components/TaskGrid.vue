<template>
    <div v-if="tasks.length" class="task-grid">
        <TaskCard v-for="task in tasks" :key="task.name"
            @taskDeleted="$emit('taskDeleted', $event)"
            @taskStateChanged="$emit('taskStateChanged', $event)"
            :task="task">
        </TaskCard>
    </div>
    <p v-else class="no-task">Sua vida está em dia :)</p>
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
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .task-grid .task {
        margin: 10px
    }

    .no-task {
        color: #AAA;
        font-size: 1.7rem
    }

</style>