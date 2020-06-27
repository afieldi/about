<template>
    <div class="skill-bubble">
        {{skill}}
    </div>
</template>

<script>
export default {
    props: [
        "skill"
    ],
    data: function () {
        return {
            skill: this.skill
        }
    }
}
</script>

<style scoped>
.skill-bubble {
    background-color: rgb(61, 61, 61);
    color: white;
    display: inline-block;
    padding: 5px 10px;
    margin: 5px;
    border-radius: 15px;
}
</style>
