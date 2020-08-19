<template>
    <header class="header">
        <h2>Stuff I need todo</h2>
        <div id="nav">
            <router-link to="/">Home</router-link>&nbsp;| &nbsp;<router-link
                to="/about"
                >About</router-link
            >
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
};
</script>

<style scoped>
#nav a {
    font-weight: bold;
    font-size: 0.9em;
}
#nav a.router-link-exact-active {
    color: #42b983;
}
.header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.header h2 {
    font-size: 1.2em;
    letter-spacing: 0.5px;
}
.header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
}
</style>
