<template>
    <nav class="nav">
        <div class="logo">
            <a class="txt-logo text-decoration-none" href="#"><b> CINO</b>CHE </a>
            <!-- <span class="subheader">efefeefe</span> -->
            </div>
            <div class="links">
            <ul class="link-grp">
                <li>
                    <a class="link-item text-right" href="#">About us</a>
                </li>
            </ul>
            </div>
        
    </nav>

</template>


<style scoped>
nav {
    display: flex;
    height: 5rem;
    justify-content: space-between;
    align-items: center;
    /* margin-bottom: 10px; */
    font-weight: lighter;
    letter-spacing: 0.5px;
    background-color: rgb(31, 30, 30);
    /* opacity:0.2;  */
}
.nav .logo{
    
    display: flex;
    flex-direction: column;
    height: 100%;
    font-size: 50px;
    justify-content: center;
    text-decoration: none;
}

.txt-logo{
    height: 100%;
    color: rgb(255, 255, 255);
    font-style: italic;
}
.link-grp{
    list-style-type: none;
}
.link-item{
    text-decoration: none;
    list-style: none;
    font-size: 20px;
    color: rgb(255, 255, 255);
    margin-right: 15px;
}
</style>


<script>
export default{}
</script>