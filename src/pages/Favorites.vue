<script setup>
import { ref, onMounted } from 'vue'
import CardList from '../components/CardList.vue'

import api from '../Axios'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await api.get('/favorites?_relations=items')
    favorites.value = data.map((obj) => obj.item)
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <h2 class="text-3xl font-bold mb-8">Мои Избранные</h2>
  <CardList :items="favorites" is-favorites />
</template>
