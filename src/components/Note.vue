<script setup>
import { reactive, useTemplateRef } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';
import { onBeforeMount, onMounted, onUpdated } from 'vue';

const notes = reactive([]);
const note = ref('');
const noteInput = useTemplateRef('noteInput');
const notesList = useTemplateRef('noteList');

const addNote = () => {
    if (note.value.trim() !== '') {
        notes.push(note.value.trim());
        note.value = '';
        noteInput.value.focus();// Set focus back to the input field
        if (notesList.value) {
            // Scroll to the bottom of the list
            const lastNote = notesList.value[notesList.value.length - 1];
            lastNote.scrollIntoView({ behavior: 'smooth' });
        }
    }
};
onBeforeMount(() => {
    console.log('Note component is about to be mounted');
});

onMounted(() => {
    noteInput.value.focus(); // Set focus to the input field on mount
    console.log('Note component mounted');
});

onUpdated(() => {
    console.log('Note component updated');
});
   
</script>
<template>
    <div>
        <h1 >Notes</h1>
        <input type="text" v-model="note" ref="noteInput" placeholder="Add a note" />
        <button @click.prevent="addNote">Add Note</button>
        <ul>
            <li v-for="(n, index) in notes" :key="index" ref="noteList">{{ n }}</li>
        </ul>
    </div>
</template>
<style scoped>
    .red {
        color: red;
    }
    .bold {
        text-transform: uppercase;
        font-weight: bold;
    }
</style>