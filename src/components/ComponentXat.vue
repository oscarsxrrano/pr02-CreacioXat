<script setup>
    // imports
    import ComponentMissatge from './ComponentMissatge.vue';
    import { ref } from 'vue';

    // array de mensajes REACTIVO
    const messages = ref([]);

    // funcion para subir el emit (mensaje)
    const sendMsg = (newMsg) => {
        messages.value.push(newMsg)
    }

    // nombre del autor
    const autor = 'Usuari 1'
</script>

<template>
    <div>
        <h2>Xat entre usuaris</h2>
        <ul>
            <li v-for="(msg, index) in messages" :key="index">
                <span>{{ msg.autor }}: {{ msg.text }}</span>
            </li>
        </ul>

        <ComponentMissatge :autor = "autor" @sendMsg="sendMsg"></ComponentMissatge>
    </div>
</template>

<style scoped>

</style>