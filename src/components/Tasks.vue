<template>
    <div>
        <ul>
            <li v-for="task in tasks" v-bind:key="task.id">
                <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"/>
             </li>
        </ul>
    </div>
</template>

<script>
import Task from './Task'

export default {
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        Task
    },
    emits: ['delete-task', 'toggle-reminder']
}
</script>