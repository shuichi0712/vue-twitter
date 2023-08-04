<script setup>
  import Button from './Button.vue'
  import { ref } from 'vue'
    import router from '../router'
  const task = ref({})
  const submit = (title, content, person_in_charge) => {
    fetch('http://localhost:80/api/tasks', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify({
            title,
            content,
            person_in_charge
        })
    }).then(res => router.push('/tasks'))
  }
</script>

<template>
  <v-sheet width="300" class="mx-auto">
    <v-form>
      <v-text-field
        label="タイトル"
        v-model="task.title"
      ></v-text-field>
      <v-text-field
        label="内容"
        v-model="task.content"
      ></v-text-field>
      <v-text-field
        label="担当者"
        v-model="task.person_in_charge"
      ></v-text-field>
      <Button name="追加" block class="mt-2" @click="submit(task.title, task.content, task.person_in_charge)"/>
  </v-form>
  </v-sheet>
</template>
