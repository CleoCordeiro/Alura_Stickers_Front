<template>

    <v-row class="mt-n14">

        <v-col cols="12" xs="12" sm="6" md="4" lg="3" v-for="sticker in stickers">

            <v-card class="mx-auto my-12 rounded-xl" color="#151515">

                <v-img :src="sticker.imageUrl" class="rounded-xl" height="500px"></v-img>

            </v-card>
            <v-toolbar-title class="white--text">{{ stickers.name }}</v-toolbar-title>
            <v-btn class="donwload-button" @click="download(sticker.name, sticker.imageUrl)" block color="dark-blue"
                elevation="12">
                Download</v-btn>

        </v-col>

    </v-row>

</template>

<script>
export default {
    mame: 'Stickers',
    data() {
        return {
            stickers: [],
        }
    },
    mounted() {
        // this.getStickers(this.searchTerm);
        this.getStickers();
    },
    methods: {
        getStickers() {
            const components = require.context('../../public/stickers', true, /[A-Z]\w+\.(png)$/).keys();

            this.stickers = components.map(component => {
                return {
                    imageUrl: '/stickers/' + component.split('/')[1],
                    name: component.split('/')[1].split('.')[0]
                }
            });


        },
        stickersLink(image) {
            window.open(image, '_blank').focus();
        },
        download(name, image) {
            var FileSaver = require('file-saver');
            FileSaver.saveAs(image, name);
            FileSaver.saveAs

        },
        formatPrice(price) {
            const val = Number(price.toString().replace(",", "."));
            if (!val) return '0,00';
            const valueString = val.toFixed(2).replace(".", ",");
            return valueString.replace(/\B(?=(\d{3})+(?!\d))/g, ".");

        }
    }
}
</script>

<style scoped>
.white--text {
    font-size: 20px !important;
    text-align: center !important;
    color: #FFFFFF !important;

}



.ImagemStickers {
    cursor: pointer;
}


.donwload-button {
    color: #FFFFFF;
    background: -webkit-linear-gradient(left, #4b086d, #ACC0FE);
    background: -moz-linear-gradient(left, #4b086d, #ACC0FE);
    background: -ms-linear-gradient(left, #4b086d, #ACC0FE);
    background: -o-linear-gradient(left, #4b086d, #ACC0FE);
    background: linear-gradient(to right, #4b086d, #ACC0FE);
}
</style>

