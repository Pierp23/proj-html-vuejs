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
            },
            lifestyleStories: {
                successPost: {
                    user: 'Demo',
                    date: 'December 26, 2022',
                    img: 'success-story.webp',
                    title: 'The Best Success Stories',
                    type: 'Culture'
                },
                asidePosts: {
                    alonePost: {
                        user: 'Demo',
                        date: 'December 26, 2022',
                        img: 'travel-alone.webp',
                        title: 'Traveling Alone Is Awesome',
                        type: 'Stories'
                    },
                    sucessPost: {
                        user: 'Demo',
                        date: 'December 25, 2022',
                        img: 'best-places.webp',
                        title: 'Places For A Road Trip',
                        type: 'Lifestyle'
                    },
                    musicPost: {
                        user: 'Demo',
                        date: 'December 25, 2022',
                        img: 'anime-fashion.webp',
                        title: 'Music The Love Of My Life',
                        type: 'Culture'
                    }
                }

            },
            featuredPosts: {
                animePost: {
                    date: 'December 26, 2022',
                    text: 'Lorem ipsum dolor sit amet, conse ctetur adipiscing elit. Sed maximus orci ac condi mentum...',
                    img: 'photographers-mistakes.webp',
                    title: 'Live Ideas You Might Be Anime',
                    type: ['Culture', 'Stories']
                },
                francePost: {
                    date: 'December 26, 2022',
                    text: 'Lorem ipsum dolor sit amet, conse ctetur adipiscing elit. Sed maximus orci ac condi mentum...',
                    img: 'visit-france.webp',
                    title: 'Reasons To Visit France',
                    type: ['Lifestyle', 'Travel']
                },
                alonePost: {
                    date: 'December 26, 2022',
                    text: 'Lorem ipsum dolor sit amet, conse ctetur adipiscing elit. Sed maximus orci ac condi mentum...',
                    img: 'travel-alone.webp',
                    title: 'Traveling Alone Is Awesome',
                    type: ['Stories', 'Travel']
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
        <section class="middle-banner">
            <div class="container">
                <div class="banner-div">
                    <img src="../assets/img/page-banner-1-768x71.webp" alt="banner">
                </div>
            </div>
        </section>
        <section class="lifestyle-stories">
            <div class="container">
                <div class="row">
                    <div class="col">
                        <h2>
                            Lifestyle & Stories
                        </h2>
                    </div>
                    <div class="col">
                        <div class="categories">
                            <div>
                                ALL
                            </div>
                            <div>
                                LIFESTYLE
                            </div>
                            <div>
                                STORIES
                            </div>
                        </div>
                    </div>

                </div>
                <div class="row-cards">
                    <div class="col-left">
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${lifestyleStories.successPost.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ lifestyleStories.successPost.type }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ lifestyleStories.successPost.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ lifestyleStories.successPost.date }}
                                </span>
                                <div>
                                    {{ lifestyleStories.successPost.title }}
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-rigth">
                        <div class="mini-container" v-for="(asideCard, index) in lifestyleStories.asidePosts" :key="index">
                            <div class="div-img-aside">
                                <img :src="getImg(`../assets/img/${asideCard.img}`)" alt="">
                                <div class="card-type">
                                    {{ asideCard.type }}
                                </div>
                            </div>
                            <div class="info-aside-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ asideCard.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ asideCard.date }}
                                </span>
                                <div>
                                    {{ asideCard.title }}
                                </div>
                            </div>
                        </div>

                    </div>

                </div>

            </div>

        </section>

        <section class="featured-posts">
            <div class="container">
                <h2>
                    Featured Posts
                </h2>
                <div class="row">
                    <div class="my-col" v-for="(card, i) in featuredPosts" :key="i">
                        <div class="card-img">
                            <img :src="getImg(`../assets/img/${card.img} `)" alt="">
                            <div class="mini-card">
                                <span>{{ card.type[0] }}</span>
                                <span>{{ card.type[1] }}</span>
                            </div>
                        </div>
                        <div class="card-info">
                            <h4>
                                {{ card.title }}
                            </h4>
                            <p>
                                {{ card.date }}
                            </p>
                            <p class="text">
                                {{ card.text }}
                            </p>
                            <a href="#">
                                Read more
                            </a>
                        </div>

                    </div>

                </div>
            </div>

        </section>
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

    & .container {
        width: 1000px;
        margin: 0 auto;
    }

    & .middle-banner {
        background-color: $third-color;
        padding: 20px 0;

        & .banner-div {
            margin: 0 auto;
            width: 100%;
            height: 90px;

            & img {
                width: 100%;
                height: 100%;
            }
        }
    }

    & .lifestyle-stories {
        & .container {
            & .row {
                display: flex;
                justify-content: space-between;

                & .col {
                    & h2 {
                        text-transform: uppercase;
                    }

                    .categories {
                        display: flex;

                        & div {
                            margin: 0 5px;
                            padding: 5px 10px;
                            background-color: $fourth-color;
                            color: $secondary-color;
                            border-radius: 5px;
                        }
                    }
                }
            }

            & .row-cards {
                display: flex;
                justify-content: left;

                .col-left {
                    width: calc(100% / 5) * 3;
                    margin-right: 20px;

                    & .div-img {
                        position: relative;

                        & img {
                            width: 100%;
                            filter: brightness(0.5);
                        }

                        & .mini-card {
                            position: absolute;
                            top: 10px;
                            left: 10px;

                            & span {
                                padding: 2px 10px;
                                margin: 2px;
                                border: 1px solid black;
                                border-radius: 5px;
                                background-color: $third-color;

                            }
                        }

                        & .info-card {
                            position: absolute;
                            bottom: 20px;
                            left: 20px;
                            color: $secondary-color;
                            font-weight: bold;

                            & span {
                                padding: 0 5px;
                            }

                            & div {
                                padding: 5px 0;
                            }
                        }
                    }
                }

                & .mini-container {
                    display: flex;
                    justify-content: left;
                    align-items: center;
                    border-bottom: 1px solid black;

                    & .div-img-aside {
                        width: 150px;
                        height: 100px;
                        margin: 10px 0;
                        position: relative;

                        & .card-type {
                            position: absolute;
                            top: 5px;
                            left: 10px;
                            padding: 2px 10px;
                            margin: 2px;
                            border: 1px solid black;
                            border-radius: 5px;
                            background-color: $third-color;
                        }

                        & img {
                            width: 100%;
                            height: 100%;
                            object-fit: cover;
                            border-radius: 10px;
                            filter: brightness(0.7);
                        }
                    }

                    & .info-aside-card {
                        padding-left: 10px;

                        & span {
                            padding: 0 5px;
                        }

                        & div {
                            padding: 5px 0;
                        }
                    }
                }
            }
        }
    }

    & .featured-posts {

        & h2 {
            text-transform: uppercase;
            padding: 10px 0;
        }

        & .row {
            display: flex;
            justify-content: space-between;

            & .my-col {
                width: calc(100% / 3 - 10px);

                & .card-img {
                    width: 100%;
                    height: 200px;
                    position: relative;


                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }

                    & .mini-card {
                        position: absolute;
                        top: 10px;
                        left: 50%;
                        transform: translate(- 50%);


                        & span {
                            padding: 2px 10px;
                            margin: 2px;
                            border: 1px solid black;
                            border-radius: 5px;
                            background-color: $third-color;

                        }
                    }
                }

                & .card-info {
                    text-align: center;
                    padding: 20px 0;
                    background-color: $third-color;

                    & .text {
                        padding-top: 10px;
                        margin-bottom: 20px;
                    }

                    & a {
                        padding: 5px 15px;
                        background-color: $main-color;
                        border-radius: 20px;
                        color: $secondary-color;
                        text-decoration: none;
                    }
                }
            }
        }
    }

    & .main-bottom {
        padding: 20px 0;

        & .row {
            display: flex;
            justify-content: space-between;

            & .col-2 {

                width: calc(100% / 6 - 5px);
                margin: 0 5px;

                & .img-div {
                    width: 100%;
                    height: 150px;
                    position: relative;

                    &:hover img {
                        cursor: pointer;
                        filter: brightness(0.9);
                    }

                    &:hover h3 {
                        cursor: pointer;
                        text-shadow: 0 0 1px black, 0 0 1px black, 0 0 1px black, 0 0 1px black;
                    }

                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        filter: brightness(0.7);
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
}
</style>
