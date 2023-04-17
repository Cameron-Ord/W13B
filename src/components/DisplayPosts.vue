<template>
    <div class="parent">

        <!-- creating the parent div and setting the button to call the toggle_layout function -->

        <button @click="toggle_layout">toggle</button>

        <article ref="display_article">

            <!-- selecting the article as a ref -->

            <span v-for="(array, counter) in arrays" :key="counter">

                <!-- creating the for loop which injects the spans with the content from the array of objects-->

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

       //this function assigns a grid, sets grid-template-columns if it is undefined as such, then deletes any grid-template-rows style attributes//

            if(this.$refs[`display_article`][`style`][`grid-template-columns`] !== `1fr 1fr 1fr`){
                this.$refs[`display_article`][`style`][`grid-template-rows`] = null;
                this.$refs[`display_article`][`style`][`display`] = `grid`;
                this.$refs[`display_article`][`style`][`grid-template-columns`] = `1fr 1fr 1fr`;
            } else {

                //the else statement of this function removes the columns style attribute and adds a row template instead//
                this.$refs[`display_article`][`style`][`grid-template-columns`] = null;
                
                this.$refs[`display_article`][`style`][`grid-template-rows`] = `1fr 1fr 1fr`;
            }



        }

    },


    data() {
        return {

            arrays: [

            //adding variables to refer to//
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