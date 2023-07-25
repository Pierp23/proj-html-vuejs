<script>
export default {
    name: "MainComponent",
    data() {
        return {
            scroll: {
                food: {
                    title: 'FOOD',
                    img: 'healthy-foods.webp',
                    mainType: 'Food',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: 'The Best Healthy Food In 2022'
                },
                winter: {
                    title: 'WINTER',
                    img: 'winter.webp',
                    mainType: 'Fashion',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: 'The Best Winter Outfits'
                },
                mistakes: {
                    title: 'MISTAKES',
                    img: 'photographers-mistakes.webp',
                    mainType: 'Fashion',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: "Begginer Photograper's Mistakes"
                },
                ideas: {
                    title: 'IDEAS',
                    img: 'ideas-anime.webp',
                    mainType: 'Culture',
                    secondType: 'Stories',
                    date: 'December 26, 2022',
                    description: "Live Ideas You Might Be Anime"
                }
            },
            topics: {
                fashion: {
                    title: 'FASHION',
                    img: 'anime-fashion.webp',
                    mainType: 'Fashion',
                    secondType: 'Lifestyle',
                    description: 'Fashion Trend Now A Day',
                    user: 'Demo',
                    date: 'December 25, 2022',

                },
                culture: {
                    title: 'CULTURE',
                    img: 'success-story.webp',
                    mainType: 'Culture',
                    secondType: 'Lifestyle',
                    description: 'Music The Love Of My Life',
                    user: 'Demo',
                    date: 'December 25, 2022',

                },
                food: {
                    title: 'FOOD',
                    img: 'healthy-foods.webp'
                },
                lifestyle: {
                    title: 'LIFESTYLE',
                    img: 'visit-france.webp',
                    mainType: 'Lifestyle',
                    secondType: 'Travel',
                    description: 'Reasons To Visit France',
                    user: 'Demo',
                    date: 'December 26, 2022',
                },
                stories: {
                    title: 'STORIES',
                    img: 'travel-alone.webp',
                    mainType: 'Stories',
                    secondType: 'Travel',
                    description: 'Traveling Alone Is Awesome',
                    user: 'Demo',
                    date: 'December 26, 2022',

                },
                travel: {
                    title: 'TRAVEL',
                    img: 'best-places.webp',
                    mainType: 'Lifestyle',
                    secondType: 'Stories',
                    thirdType: 'Travel',
                    description: 'Places For A Road Trip',
                    user: 'Demo',
                    date: 'December 25, 2022',
                }
            },
            lifestyleStories: {
                successPost: {
                    user: 'Demo',
                    date: 'December 26, 2022',
                    img: 'success-story.webp',
                    description: 'The Best Success Stories',
                    mainType: 'Culture'
                },
                asidePosts: {
                    alonePost: {
                        user: 'Demo',
                        date: 'December 26, 2022',
                        img: 'travel-alone.webp',
                        description: 'Traveling Alone Is Awesome',
                        mainType: 'Stories'
                    },
                    sucessPost: {
                        user: 'Demo',
                        date: 'December 25, 2022',
                        img: 'best-places.webp',
                        description: 'Places For A Road Trip',
                        mainType: 'Lifestyle'
                    },
                    musicPost: {
                        title: 'CULTURE',
                        img: 'music-love.webp',
                        mainType: 'Culture',
                        secondType: 'Lifestyle',
                        description: 'Music The Love Of My Life',
                        user: 'Demo',
                        date: 'December 25, 2022',

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
        <section class="scroll-div">
            <div class="row">
                <span class="prev">
                    <i class="fa-solid fa-chevron-left"></i>
                </span>
                <span class="next">
                    <i class="fa-solid fa-chevron-right"></i>
                </span>
                <div class="my-col" v-for="(cardScroll, index) in scroll" :key="index">
                    <div class="img-container">
                        <img :src="getImg(`../assets/img/${cardScroll.img} `)" :alt="cardScroll.title">
                        <div class="mini-card">
                            <span>
                                {{ cardScroll.mainType }}
                            </span>
                            <span v-if="cardScroll.secondType !== ''">
                                {{ cardScroll.secondType }}
                            </span>
                        </div>
                    </div>
                    <div class="infos">
                        <div class="description">
                            {{ cardScroll.description }}
                        </div>
                        <div class="date-info">
                            {{ cardScroll.date }}
                        </div>
                    </div>
                </div>
            </div>

        </section>


        <section class="animes">
            <div class="container">
                <div class="row">
                    <div class="col-3">
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${topics.fashion.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ topics.fashion.mainType }}
                                </span>
                                <span>
                                    {{ topics.fashion.secondType }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ topics.fashion.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ topics.fashion.date }}
                                </span>
                                <div>
                                    {{ topics.fashion.description }}
                                </div>
                            </div>
                        </div>
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${topics.stories.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ topics.stories.mainType }}
                                </span>
                                <span>
                                    {{ topics.stories.secondType }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ topics.stories.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ topics.stories.date }}
                                </span>
                                <div>
                                    {{ topics.stories.description }}
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-6">
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${topics.travel.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ topics.travel.mainType }}
                                </span>
                                <span>
                                    {{ topics.travel.secondType }}
                                </span>
                                <span>
                                    {{ topics.travel.thirdType }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ topics.travel.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ topics.travel.date }}
                                </span>
                                <div>
                                    {{ topics.travel.description }}
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-3">
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${lifestyleStories.asidePosts.musicPost.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ lifestyleStories.asidePosts.musicPost.mainType }}
                                </span>
                                <span>
                                    {{ lifestyleStories.asidePosts.musicPost.secondType }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ lifestyleStories.asidePosts.musicPost.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ lifestyleStories.asidePosts.musicPost.date }}
                                </span>
                                <div>
                                    {{ lifestyleStories.asidePosts.musicPost.description }}
                                </div>
                            </div>
                        </div>
                        <div class="div-img">
                            <img :src="getImg(`../assets/img/${topics.lifestyle.img}`)" alt="">

                            <div class="mini-card">
                                <span>
                                    {{ topics.lifestyle.mainType }}
                                </span>
                                <span>
                                    {{ topics.lifestyle.secondType }}
                                </span>
                            </div>
                            <div class="info-card">
                                <span>
                                    <i class="fa-solid fa-user"></i>
                                    {{ topics.lifestyle.user }}
                                </span>
                                <span>
                                    <i class="fa-regular fa-calendar"></i>
                                    {{ topics.lifestyle.date }}
                                </span>
                                <div>
                                    {{ topics.lifestyle.description }}
                                </div>
                            </div>
                        </div>
                    </div>
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
                                    {{ lifestyleStories.successPost.mainType }}
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
                                    {{ lifestyleStories.successPost.description }}
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-rigth">
                        <div class="mini-container" v-for="(asideCard, index) in lifestyleStories.asidePosts" :key="index">
                            <div class="div-img-aside">
                                <img :src="getImg(`../assets/img/${asideCard.img}`)" alt="">
                                <div class="card-type">
                                    {{ asideCard.mainType }}
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
                                    {{ asideCard.description }}
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="middle-banner">
            <div class="container">
                <div class="banner-div">
                    <img src="../assets/img/page-banner-1-768x71.webp" alt="banner">
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

    & .scroll-div {
        background-color: $third-color;
        padding: 20px;

        & .row {
            display: flex;
            justify-content: space-between;
            position: relative;

            & .prev {
                font-size: 15px;
                font-weight: bolder;
                text-align: center;
                line-height: 20px;
                background-color: $secondary-color;
                border-radius: 50%;
                width: 20px;
                height: 20px;
                color: $fourth-color;
                position: absolute;
                top: 50%;
                left: 10px;
                z-index: 1
            }

            & .next {
                font-size: 15px;
                font-weight: bolder;
                text-align: center;
                line-height: 20px;
                background-color: $secondary-color;
                border-radius: 50%;
                width: 20px;
                height: 20px;
                color: $fourth-color;
                position: absolute;
                top: 50%;
                right: 10px;
                z-index: 1
            }

            & .next:hover,
            & .prev:hover {
                background-color: $main-color;
            }


            & .my-col {
                width: calc(100% / 4 - 10px);
                margin: 0 5px;

                background-color: $secondary-color;

                & .img-container {
                    width: 100%;
                    position: relative;


                    & img {
                        width: 100%;
                        object-fit: cover;
                    }

                    & .mini-card {
                        position: absolute;
                        top: 20px;
                        left: 50%;
                        transform: translate(-50%);

                        & span {
                            padding: 2px 10px;
                            margin: 2px;
                            border: 1px solid black;
                            border-radius: 5px;
                            background-color: $third-color;

                        }
                    }
                }

                & .infos {
                    text-align: center;
                    padding: 5px 0;

                    & .description {
                        font-weight: bold;
                    }

                    & .date-info {
                        font-size: 10px;
                    }
                }


            }
        }
    }

    & .animes {
        padding: 50px 0;

        .row {
            display: flex;
            justify-content: space-between;

            & .col-3 {
                display: flex;
                flex-direction: column;

                & .div-img {
                    position: relative;
                    width: 100%;
                    height: 200px;
                }

                & .div-img:first-child {
                    margin-bottom: 10px;
                }
            }

            & .col-6 {
                display: flex;

                & .div-img {
                    position: relative;
                    width: 100%;
                    height: 100%;
                    margin: 0 5px;
                }
            }

            & img {
                width: 100%;
                height: 100%;
                object-fit: cover;
                border-radius: 10px;
                filter: brightness(0.5);
            }

            & .mini-card {
                position: absolute;
                top: 20px;
                left: 50%;
                transform: translate(-50%);

                & span {
                    padding: 2px 10px;
                    margin: 2px;
                    border: 1px solid black;
                    border-radius: 5px;
                    background-color: $third-color;

                }
            }

            & .info-card {
                text-align: center;
                width: max-content;
                position: absolute;
                bottom: 10px;
                left: 50%;
                transform: translate(-50%);
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
