<template>
    <div :class="{ isActive: myClass }">
        <h1>
            {{ header }}
        </h1>
    </div>
</template>
<script>
export default{
    name: 'SectionOne',
    props:['header'],
    data(){
        return{
            myClass: true,
        }
    }
}
</script>

<style scoped>
    .isActive{
        /* background-color: blue; */
        background-color: green;
        color: white;
        width: 250px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-transform: capitalize;
        padding: 5px 0;
        border-radius: 8px;
    }
</style>