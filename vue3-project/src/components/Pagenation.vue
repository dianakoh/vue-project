<template>
    <nav aria-label="Page navigation example">
        <ul class="pagination">
        <li v-if="currentPage !== 1" class="page-item">
            <a style="cursor: pointer" class="page-link" @click="getTodos(currentPage - 1)">Previous</a>
        </li>
        <li
            v-for="page in numberOfPages"
            :key="page" 
            class="page-item"
            :class="currentPage === page ? 'active' : ''"
        >
            <a style="cursor: pointer" class="page-link" @click="getTodos(page)">{{page}}</a>
        </li>
        <li v-if="numberOfPages !== currentPage" class="page-item">
            <a style="cursor: pointer" class="page-link" @click="getTodos(currentPage + 1)">Next</a>
        </li>
        </ul>
    </nav>
</template>
<script>
export default {
    props: {
        numberOfPages: {
            type: Number,
            required: true
        },
        currentPage: {
            type: Number,
            required: true
        }
    },
    emits: ['get-todos'],
    setup(props, {emit}) {
        const getTodos = (page) => {
            emit('get-todos', page);
        };
        
        return {
            getTodos
        }
    }
}

</script>
<style scoped>

</style>
