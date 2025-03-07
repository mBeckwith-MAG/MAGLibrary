<script setup>
import { ref } from 'vue'
import NavPageLink from './components/NavPageLink.vue';
import MorphingNav from './components/MorphingNav.vue';
import BasicButton from './components/BasicButton.vue';
import BasicInput from './components/BasicInput.vue';
import BasicResult from './components/BasicResult.vue';

const inputTest = ref(null)
</script>

<template>
  <MorphingNav>
    <template #left-links>
      <BasicButton>Home</BasicButton>
      <BasicButton>VW Calc</BasicButton>
      <BasicButton>Sls Bns</BasicButton>
    </template>
    <template #right-links>
      <BasicButton>MB</BasicButton>
    </template>
    <template #content>
      <BasicInput label="Yep" input-type="text" input-placeholder="ok then" focus-color="focus:border-purple-400" v-model="inputTest" />
      <BasicResult label="result" :result="inputTest" class="mt-2" />
    </template>
  </MorphingNav>
</template>
