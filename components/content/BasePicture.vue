<template>
    <div>
        <v-img :src="url" :transition="false" />
        <slot />
    </div>

</template>

<script setup lang="ts">
interface IProps {
    src: string;
}
const props = defineProps<IProps>()
const $img = useImage();
const url = $img(props.src,
    { width: 500, quality: 70, format: 'webp' })

</script>