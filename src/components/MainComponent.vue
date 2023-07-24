<script>
export default {
    name: "MainComponent",
    data() {
        return {
            topics: {
                fascion: {
                    title: 'FASHION',
                    img: 'anime-fashion.webp'
                },
                culture: {
                    title: 'CULTURE',
                    img: 'success-story.webp'
                },
                food: {
                    title: 'FOOD',
                    img: 'healthy-foods.webp'
                },
                lifestyle: {
                    title: 'LIFESTYLE',
                    img: 'visit-france.webp'
                },
                stories: {
                    title: 'STORIES',
                    img: 'travel-alone.webp'
                },
                travel: {
                    title: 'TRAVEL',
                    img: 'best-places.webp'
                }




            }
        }
    },
    props: {},
    methods: {
        getImg: function (imgX) {
            return new URL(imgX, import.meta.url).href
        }

    }
}
</script>

<template>
    <main>
        <section class="main-bottom">
            <div class="row">
                <div class="col-2" v-for="(topic, index) in topics" :key="index">
                    <div class="img-div">
                        <img :src="getImg(`../assets/img/${topic.img} `)" :alt="topic.title">
                        <h3>
                            {{ topic.title }}
                        </h3>
                    </div>

                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/main.scss" as *;
@use "../assets/scss/reset.scss" as *;

main {
    & .main-bottom {
        padding: 20px 0;

        & .row {
            display: flex;

            & .col-2 {

                width: calc(100% / 6 - 5px);
                margin: 0 5px;

                & .img-div {
                    max-width: 200px;
                    height: 150px;
                    position: relative;

                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        filter: brightness(0.7);
                    }
                }

                & h3 {
                    color: $secondary-color;
                    font-weight: bold;
                    position: absolute;
                    top: 50%;
                    left: 50%;
                    transform: translate(- 50%, - 50%);
                }

            }
        }
    }
}
</style>
