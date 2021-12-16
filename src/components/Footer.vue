<template>
    <footer>
        <div class="left">
            <ul>
                <li><img src="../assets/logo.png" alt='picture of logo'></li>
                <li><img src="../assets/copyright.svg"></li>
                <li><img src='../assets/socials.svg'></li>
            </ul>
            </div>

            <ul class='ul'>
                <li class='get'>Get in touch</li>
                <li><p class='partner'> Partnerships & general enquires
                    partnaship@enyata.com</p></li>
                <li>Greater Accra, Accra, Ghana.</li>
            </ul>
    </footer>
</template>

<style scoped>
footer{
    padding: 70px;
    display: flex;
    gap: 200px;
    border-top: 3px solid rgba(255, 255, 255, 0.25);
}
ul{
    list-style-type: none;
}
ul li{
    margin-bottom: 30px;
}
.get{
    font-weight: bold;
    font-size: 16px;
    text-transform: uppercase;
}
.partner{
    width:300px;
}

@media screen and (max-width:765px) {
    footer{
    display: block;
}
}
</style>


