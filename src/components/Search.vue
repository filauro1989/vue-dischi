<template>
    <select @change="$emit('doSelect', selectedValue)" v-model="selectedValue" name="genreSelect" id="genreSelect">
        <option value="all">All</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            selectedValue: '',
        }
    },
}
</script>

<style>

</style>