<template>
    <div class="btn">
        <NuxtLink to="/">Home page</NuxtLink>
    </div>
</template>


<script>
export default{
    name:'navbar'
}

</script>
<style>
.btn{
    display: flex;
    justify-content: center;
    align-content: center;
}
.btn a{
    width: 100%;
    height: 4rem;
    background: black;
    color: beige;
    font-size: 2rem;
    text-align: center;
    text-decoration: none;
}
</style>