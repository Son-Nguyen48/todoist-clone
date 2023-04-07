<template>
  <div class="px-5">
    <ul>
      <li v-for="(task, index) in tasks" :key="task.id" class="task-item">
        <task-item
          :data="task"
          :index="index"
          @toggle-edit-task-form="toggleEditTaskForm"
          @edit-task="editTask"
          @delete-task="deleteTask"
        ></task-item>
      </li>

      <li class="task-item__add">
        <form-add-task @add-task="addTask"></form-add-task>
      </li>
    </ul>
  </div>
</template>

<script>
import TaskItem from "./TaskItem.vue";
import FormAddTask from "./FormAddTask.vue";

export default {
  data() {
    return {
      tasks: [
        {
          id: 1,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 2,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 3,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 3,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 2,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 4,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 4,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 5,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 2,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 6,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 7,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 3,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        }
      ]
    };
  },
  components: {
    TaskItem,
    FormAddTask
  },
  methods: {
    addTask(data) {
      data.id = this.tasks.length + 1;
      this.tasks.push(data);
    },

    toggleEditTaskForm(index) {
      this.tasks[index].isEditTaskFormOpen =
        !this.tasks[index].isEditTaskFormOpen;
    },

    editTask(data) {
      this.tasks = this.tasks.map((i) => (i.id === data.id ? data : i));
      console.log(this.tasks, "tasks");
    },

    deleteTask(data) {
      if (!data) return;
      else this.tasks.splice(data, 1);
    }
  }
};
</script>

<style scoped>
ul {
  padding: 0;
  margin: 0;
}

.task-item {
  border-bottom: 1px solid #f0f0f0;
}
</style>
