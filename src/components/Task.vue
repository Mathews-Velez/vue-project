<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-square-x"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
          <rect x="4" y="4" width="16" height="16" rx="2"></rect>
          <path d="M10 10l4 4m0 -4l-4 4"></path>
        </svg>
      </i>
    </h3>
    <p>{{ task.day }}</p>
    <p>
      at {{ task.time }} 
      <div class="editBtn">
        <i
        @click="$emit('delete-task', task.id)"
        class="fas fa-arrow-circle-right-"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-edit"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          color="white"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
          <path
            d="M9 7h-3a2 2 0 0 0 -2 2v9a2 2 0 0 0 2 2h9a2 2 0 0 0 2 -2v-3"
          ></path>
          <path d="M9 15h3l8.5 -8.5a1.5 1.5 0 0 0 -3 -3l-8.5 8.5v3"></path>
          <line x1="16" y1="5" x2="19" y2="8"></line></svg
      ></i>
      </div>
    </p>
    <h3>
      <div></div>
    </h3>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scope>
.editBtn{
  text-align: right;
  align-items: end;
}
.fa {
  text-align: right;
  align-items: end;
  color: red;
}
.fa-pencil {
  color: whitesmoke;
}

.task {
  background-color: #082032;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>