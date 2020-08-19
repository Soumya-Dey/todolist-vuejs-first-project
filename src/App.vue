<template>
    <div id="app">
        <Header />
        <router-view />
    </div>
</template>

<script>
import Header from "./components/Header";

export default {
    name: "App",
    components: { Header },
};
</script>

<style>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

body {
    font-family: Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    line-height: 1.4;
}

.container {
    padding: 16px 16px 46px 16px;
}

.btn {
    display: inline-block;
    border: none;
    background: #333;
    color: #fff;
    padding: 12px 16px;
    cursor: pointer;
}
.btn:hover {
    background: #666;
}
</style>
