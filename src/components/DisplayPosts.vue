<template>
    <div class="parent">

        <button @click="toggle_layout">toggle</button>

        <article ref="display_article">

            <span v-for="(array, counter) in arrays" :key="counter">
                <h3>{{ array[`user`] }}</h3>

                <p>{{ array[`content`] }}</p>

                <h3>{{ array[`date_created`] }}</h3>
            </span>


        </article>
    </div>
</template>

<script>


export default {



    methods: {

        toggle_layout: function(){

       

            if(this.$refs[`display_article`][`style`][`grid-template-columns`] !== `1fr 1fr 1fr`){

                this.$refs[`display_article`][`style`][`grid-template-rows`] = null;

                this.$refs[`display_article`][`style`][`display`] = `grid`;
                this.$refs[`display_article`][`style`][`grid-template-columns`] = `1fr 1fr 1fr`;
            } else {
                this.$refs[`display_article`][`style`][`grid-template-columns`] = null;
                
                this.$refs[`display_article`][`style`][`grid-template-rows`] = `1fr 1fr 1fr`;
            }



        }

    },


    data() {
        return {

            arrays: [

                {

                    content: `lorem ipsum lorem ipsum`,

                    user: `Dylan`,

                    date_created: `10 - 23 - 2020`


                },

                {

                    content: `lorem ipsum lorem ipsum`,

                    user: `Jacob`,

                    date_created: `08 - 10 - 2012`


                },

                {

                    content: `lorem ipsum lorem ipsum`,

                    user: `Avery`,

                    date_created: `11 - 03 -2019`


                },
            ]
        }


    },
}
</script>

<style scoped>
.parent{

display: grid;

justify-items: center;

align-items: center;

grid-template-rows: 100px 450px;

width: 100%;



}

article{

width: 100%;

}

span{

    display: grid;

    align-items: center;

    justify-items: center;

    text-align: center;

    grid-template-rows: 50px 50px 50px;



}

</style>