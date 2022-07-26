<template>

    <v-container fluid>
        <v-row justify="center" align="center">
            <v-col cols="12" xs="12" sm="6" md="4">

                <v-toolbar-title class="white--text" justify="center" align="center">Nome do Sticker</v-toolbar-title>
                <v-text-field v-model="name" label="Digite o nome do sticker" dark filled solo flat
                    background-color="transparent" rounded outlined>
                </v-text-field>
                <v-spacer></v-spacer>
                <v-toolbar-title class="white--text" justify="center" align="center">Texto do Sticker</v-toolbar-title>
                <v-text-field v-model="textoSticker" label="Digite o texto do sticker" dark filled solo flat
                    background-color="transparent" rounded outlined>
                </v-text-field>
                <v-toolbar-title class="white--text" justify="center" align="center">URL do Sticker</v-toolbar-title>
                <v-text-field v-model="imageUrl" label="Digite a URL do sticker" dark filled solo flat
                    background-color="transparent" rounded outlined>
                </v-text-field>
                <v-btn class="donwload-button" @click="download()" block color="dark-blue" elevation="12">
                    Criar Sticker</v-btn>
            </v-col>
        </v-row>



    </v-container>
</template>

<script>
import Axios from 'axios';

export default {
    mame: 'Search',

    data: function () {
        return {
            name: '',
            imageUrl: '',
            textoSticker: ''
        }
    },

    methods: {
        Search: function () {
            this.$root.$emit('searchEvent', this.SearchTerm);
        },
        async teste() {
            Stickerdownload.downloadImage();
        },
        async download() {
            var FileSaver = require('file-saver');



            const sticker = {
                "name": this.name,
                "imageUrl": this.imageUrl,
                "textoSticker": this.textoSticker
            };



            Axios.post('https://imersaojava.herokuapp.com/stickers', sticker, { responseType: 'blob' })
                .then(response => {
                    var filename = response.headers['content-disposition'].split('filename=')[1].replaceAll('"', '');
                    FileSaver.saveAs(new Blob([response.data]), filename);
                })
                .catch(error => {
                    console.log(error);
                });

        }
    }
}

</script>

<style scoped>
.donwload-button {
    color: #FFFFFF;
    background: -webkit-linear-gradient(left, #4b086d, #ACC0FE);
    background: -moz-linear-gradient(left, #4b086d, #ACC0FE);
    background: -ms-linear-gradient(left, #4b086d, #ACC0FE);
    background: -o-linear-gradient(left, #4b086d, #ACC0FE);
    background: linear-gradient(to right, #4b086d, #ACC0FE);
}
</style>