<script setup lang="ts">
import coursData from "./datas/cours.json";

export interface CoursType {
  id: number;
  titre: string;
  description: string;
  duree: string;
  fichier: string;
}

const cours = coursData as CoursType[];
</script>

<template>
  <div class="p-4">
    <h1 class="text-4xl font-bold my-6">
      🏋🏻‍♀️ Cours de <span class="text-accent">sport</span>
    </h1>
    <ul class="space-y-4">
      <li
        v-for="lesson in cours.slice().reverse()"
        :key="lesson.id"
        class="p-4 border rounded-xl relative cursor-pointer"
      >
        <div class="flex items-center justify-between flex-wrap-reverse gap-2">
          <h2 class="text-xl">
            {{ lesson.titre }}
          </h2>
          <p class="text-accent">{{ lesson.duree }}</p>
        </div>
        <p class="text-sm py-2">{{ lesson.description }}</p>
        <a
          :href="lesson.fichier"
          class="absolute inset-0"
          aria-label="Voir le cours"
        ></a>
      </li>
    </ul>
  </div>
</template>
