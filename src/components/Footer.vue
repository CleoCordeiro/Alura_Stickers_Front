<template>
    <div class="footer">


        <div>
            <v-toolbar-title class="white--text" justify="center" align="center">Cléo Maia Cordeiro &copy; 2022
            </v-toolbar-title>
        </div>

        <div id="socialMedia">
            <div>
                <a href="https://www.linkedin.com/in/cleocordeiro/"><img
                        src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white"
                        alt="Linkedin"></a>
            </div>
            <div>
                <a href="https://www.facebook.com/cleo.m.cordeiro/"><img
                        src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&amp;logo=facebook&amp;logoColor=white"
                        alt="Facebook"></a>

            </div>
            <div>
                <a href="https://www.instagram.com/cleomaiacordeiro/"><img
                        src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&amp;logo=instagram&amp;logoColor=white"
                        alt="Instagram"></a>
            </div>
        </div>




    </div>


</template>

<script>
export default {
    mame: 'Footer'
}
</script>

<style scoped>
.footer {
    height: 100px;
    background-color: #222;
    border-top: 4px solid #111;
    color: #FCBA03;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;

}

#socialMedia {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 400px;
    padding: 10px;

}
</style>