<template>
    <div id="footer">

        <v-row justify="center" align="center" rows="5" cols="5" justify-content="space-between">
            <v-col cols="12" xs="12" sm="6" md="4">
                <v-toolbar-title class="white--text" justify="center" align="center">Cléo Maia Cordeiro &copy; 2022
                </v-toolbar-title>

                <a href="https://www.linkedin.com/in/cleocordeiro/"><img
                        src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white"
                        alt="Linkedin"></a>

                <a href="https://www.facebook.com/cleo.m.cordeiro/"><img
                        src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&amp;logo=facebook&amp;logoColor=white"
                        alt="Facebook"></a>

                <a href="https://www.instagram.com/cleomaiacordeiro/"><img
                        src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&amp;logo=instagram&amp;logoColor=white"
                        alt="Instagram"></a>
            </v-col>




        </v-row>
    </div>


</template>

<script>
export default {
    mame: 'Footer'
}
</script>

<style scoped>
#footer {
    height: 100px;
    background-color: #222;
    border-top: 4px solid #111;
    color: #FCBA03;
    justify-content: right;
    align-items: center;
    width: 100%;
}
</style>