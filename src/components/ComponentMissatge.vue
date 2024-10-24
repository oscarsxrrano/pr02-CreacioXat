<script setup>
    import { ref } from 'vue';
    import { defineEmits, defineProps } from 'vue';

    const props = defineProps ({
        autor: String
    });

    const emit = defineEmits ([
        'sendMsg'
    ])


    const text = ref('');

    const enviarMsg = () => {
        if (text.value.trim() !== '') {
            emit('sendMsg', {
                autor: props.autor,
                text: text.value
            });

            // limpiamos el input
            text.value = '';
        }
    }

</script>

<template>
    <div>
        <input v-model="text" type="text" placeholder="Escriu al xat..." />
        <button @click="enviarMsg" >Enviar</button>
    </div>
</template>

<style scoped>

</style>