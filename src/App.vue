<template>
    <learning-resource></learning-resource>
</template>

<script>

import LearningResource from '@/components/learning-resources/LearningResource'

export default {
    name: 'App',
    components: {
        LearningResource
    },
    data() {
        return {
            storedResources: [
                {
                    id: 'official-gide',
                    title: 'Official gide',
                    description: 'The official Vue.js documentation',
                    url: 'https://v3.ru.vuejs.org/ru'
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn to Google',
                    url: 'https://google.com'
                }
            ]
        };
    },
};
</script>

<style></style>
