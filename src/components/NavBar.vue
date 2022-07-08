<template>
    <nav>
        <div class="navbar">
            <p class="para1">Where in the world?</p>
            <!-- <img class="mode-image" src="https://media.istockphoto.com/vectors/simple-flat-moon-icon-silent-sleepmode-mobile-icon-stock-vector-on-vector-id1205781763?k=20&m=1205781763&s=612x612&w=0&h=AV3kwYDt45G3iSKo7RBm3JxlEPG5h7QX7GNnexjJMBc="
                alt=""> -->
            <p class="para2">Dark mode</p>
        </div>
    </nav>
</template>
<script>
export default {
    name: "Nav-n",
};
</script>
<style lang="scss" scoped>

// .mode-image{
//     width: 50px;
//     height: 50px;
//     color: beige;
//     margin-bottom: 10px;
//     margin-left: 800px;
// }
nav{
    background-color: white;
    display: flex;
        justify-content: space-between;
        align-items: center;
        border-radius: 3px;
        box-shadow: 1px 3px 10px gainsboro;
        margin-bottom: 10px;
}
.navbar {
    display: flex;
    justify-content: space-between;
    border-radius: 3px;
}
.para1{
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        font-size: 13px;
}
.para2{
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        font-size: 13px;
        margin-left: 1200px;
}
</style>