<template>
    <div>
        <header class="header">
            <nuxt-link to="/">Dad Jokes</nuxt-link>
            <ul>
                <nuxt-link to="/">Home</nuxt-link>
                <nuxt-link to="/jokes">Jokes</nuxt-link>
                <nuxt-link to="/about">About</nuxt-link>
            </ul>
        </header>
    </div>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style scoped>
.header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    /* background-color: black;
    color: white; */
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px dotted #ccc;
    margin:0 50px 20px 50px;
}
.header ul {
    display: flex;
}
.header a{
    padding-right: 20px;
    text-decoration: none;
    color: black;
    transition: all .3s ease ;
}
.header a:hover{
    color: tomato;
}

</style>>