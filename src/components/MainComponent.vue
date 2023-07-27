<script>
export default {
    name: "MainComponent",
    data() {
        return {
            scroll: [
                {
                    title: 'FOOD',
                    img: 'healthy-foods.webp',
                    mainType: 'Food',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: 'The Best Healthy Food In 2022'
                },
                {
                    title: 'WINTER',
                    img: 'winter.webp',
                    mainType: 'Fashion',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: 'The Best Winter Outfits'
                },
                {
                    title: 'MISTAKES',
                    img: 'photographers-mistakes.webp',
                    mainType: 'Fashion',
                    secondType: '',
                    date: 'December 26, 2022',
                    description: "Begginer Photograper's Mistakes"
                },
                {
                    title: 'IDEAS',
                    img: 'ideas-anime.webp',
                    mainType: 'Culture',
                    secondType: 'Stories',
                    date: 'December 26, 2022',
                    description: "Live Ideas You Might Be Anime"
                }
            ],
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
                    img: 'ideas-anime.webp',
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

            },
            trailers: [
                {
                    number: 1,
                    title: 'Overlord Season 4 - Official Trailer 3 | AniTV',
                    image: 'sddefault.webp',

                },
                {
                    number: 2,
                    title: 'Rent A Girlfriend Season 2 - Official Trailer | AniTV',
                    image: 'hqdefault (1).jpg'
                },
                {
                    number: 3,
                    title: 'Uncle From Another World - Official Trailer 2 | AniTV',
                    image: 'travel-alone.webp'
                },
                {
                    number: 4,
                    title: 'Prima Doll - Official Trailer | AniTV',
                    image: 'sddefault.webp'
                },
                {
                    number: 5,
                    title: 'Shoot!! Goal To The Future - Official Trailer | AniTV',
                    image: 'best-places.webp'
                },
                {
                    number: 6,
                    title: 'Boolean Season 101 - Official Trailer | AniTV',
                    image: 'hqdefault (1).jpg'
                },
                {
                    number: 7,
                    title: 'Front-End Developer Final Season - Official Trailer | AniTV',
                    image: 'music-love.webp'
                }
            ],
            indexActive: 0,
        }

    },
    props: {},
    methods: {
        getImg: function (imgX) {
            return new URL(imgX, import.meta.url).href
        },
        activePost(i) {
            this.indexActive = i;
            console.log(i)
        },
        prevClick() {
            if (this.indexActive > 0) {
                this.indexActive--;
            }
            else if (this.indexActive == 0) {
                this.indexActive = this.scroll.length - 1;
            }
        },
        nextClick() {
            if (this.indexActive < this.scroll.length - 1) {
                this.indexActive++;
            }
            else if (this.indexActive == this.scroll.length - 1) {
                this.indexActive = 0;
            }
        }
    }
}
</script>

<template>
    <main>
        <section class="scroll-div">
            <div class="row">
                <span class="prev" @click="prevClick()">
                    <i class="fa-solid fa-chevron-left"></i>
                </span>
                <span class="next" @click="nextClick()">
                    <i class="fa-solid fa-chevron-right"></i>
                </span>
                <div class="my-col" v-for="(cardScroll, index) in scroll" :key="index"
                    :class="indexActive == index ? 'activeCard' : ''">
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
                    <div class="col-right">
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
                <div class="top">
                    <h2>
                        Featured Posts
                    </h2>
                    <div class="chevrons">
                        <i class="fa-solid fa-chevron-left"></i>
                        <i class="fa-solid fa-chevron-right"></i>
                    </div>
                </div>
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

        <section class="trailers">
            <div class="container">
                <div class="row">
                    <div class="my-col">
                        <div class="trailer-max-container">
                            <img :src="getImg(`../assets/img/${trailers[indexActive].image}`)"
                                :alt="trailers[indexActive].title">
                            <div class="over-icons">
                                <div class="left">
                                    <div class="tv-icon">
                                        <a href="#">
                                            <img src="../assets/img/channels4_profile.jpg" alt="logo-channel">
                                        </a>

                                    </div>
                                    <div class="title">
                                        <a href="#">
                                            {{ trailers[indexActive].title }}
                                        </a>
                                    </div>
                                </div>
                                <div class="right">
                                    <div class="watch-later">
                                        <a href="#">
                                            <i class="fa-regular fa-clock"></i>
                                            <p>
                                                Guarda più...
                                            </p>
                                        </a>

                                    </div>
                                    <div class="share">
                                        <a href="#">
                                            <i class="fa-solid fa-share"></i>
                                            <p>
                                                Condividi
                                            </p>
                                        </a>

                                    </div>
                                </div>
                            </div>
                            <div class="over-play-icon">
                                <a href="#">
                                    <i class="fa-brands fa-youtube fa-xl"></i>
                                </a>

                            </div>
                            <div class="over-link">
                                <a href="#">
                                    Guarda su <i class="fa-brands fa-youtube"></i> YouTube
                                </a>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="aside-bar" id="first-bar">
                            <div class="play-icon">
                                <i class="fa-solid fa-play fa-lg"></i>
                            </div>
                            <div class="videos">
                                <p>
                                    Video Playlist
                                </p>
                                <p>
                                    {{ trailers[indexActive].number }}/7 Videos
                                </p>
                            </div>
                        </div>
                        <div @click="activePost(index)" class="aside-bar" v-for="(trailer, index) in trailers" :key="index">
                            <div :class="indexActive == index ? 'active-number number-icon' : 'number-icon'">
                                {{ trailer.number }}
                            </div>
                            <div class="trailer-mini-container">
                                <img :src="getImg(`../assets/img/${trailer.image} `)" :alt="trailer.title">
                            </div>
                            <div class="infos">
                                <p>
                                    {{ trailer.title }}
                                </p>
                            </div>
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

                        <div class="overlay">
                            <div class="info">
                                <p>
                                    {{ topic.title }}
                                </p>
                                <p>
                                    4 POSTS
                                </p>
                            </div>

                        </div>
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
    & a {
        text-decoration: none;
        color: $secondary-color;
    }

    & .container {
        width: 1300px;
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
                font-size: 20px;
                font-weight: bolder;
                text-align: center;
                line-height: 40px;
                background-color: $secondary-color;
                border-radius: 50%;
                width: 40px;
                height: 40px;
                color: $fourth-color;
                position: absolute;
                top: 50%;
                left: 10px;
                z-index: 2;

                &:hover {
                    cursor: pointer;
                }
            }

            & .next {
                font-size: 20px;
                font-weight: bolder;
                text-align: center;
                line-height: 40px;
                background-color: $secondary-color;
                border-radius: 50%;
                width: 40px;
                height: 40px;
                color: $fourth-color;
                position: absolute;
                top: 50%;
                right: 10px;
                z-index: 2;

                &:hover {
                    cursor: pointer;
                }
            }

            & .next:hover,
            & .prev:hover {
                background-color: $main-color;
            }


            & .my-col {
                width: calc(100% / 4 - 10px);
                margin: 0 5px;
                background-color: $secondary-color;

                &.activeCard {
                    border: 1px red solid;
                    scale: 106%;
                    z-index: 1;
                }

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
                            font-size: 18px;
                            padding: 2px 10px;
                            margin: 2px;
                            border: 1px solid black;
                            border-radius: 5px;
                            background-color: $third-color;
                        }
                    }
                }

                & .infos {
                    font-size: 18px;
                    text-align: center;
                    padding: 20px 0;

                    & .description {
                        font-weight: bold;
                    }

                    & .date-info {
                        font-size: 15px;
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
            height: 500px;

            & .col-3 {
                width: calc(100% / 4 * 1);
                display: flex;
                flex-direction: column;
                justify-content: space-between;

                & .div-img {
                    position: relative;
                    width: 100%;
                    height: 100%;

                    &:hover {
                        scale: 103%;
                        cursor: pointer;
                    }
                }

                & .div-img:first-child {
                    margin-bottom: 10px;
                }
            }

            & .col-6 {
                display: flex;
                width: calc(100% / 4 * 3);

                &:hover {
                    scale: 101%;
                    cursor: pointer;
                }

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
                    font-size: 18px;
                    padding: 2px 10px;
                    margin: 2px;
                    border: 1px solid black;
                    border-radius: 5px;
                    background-color: $third-color;

                }
            }

            & .info-card {
                font-size: 15px;
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
                object-fit: cover;
            }
        }
    }

    & .lifestyle-stories {
        padding: 30px 0;

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
                            font-size: 18px;
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
                    max-height: 500px;
                    margin-right: 20px;

                    &:hover {
                        scale: 103%;
                        cursor: pointer;
                    }

                    & .div-img {
                        position: relative;
                        height: 100%;
                        width: 100%;

                        & img {
                            width: 100%;
                            height: 100%;
                            object-fit: cover;
                            filter: brightness(0.5);
                        }

                        & .mini-card {
                            font-size: 18px;
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

                            & span {
                                padding: 0 5px;
                                font-size: 18px;
                            }

                            & div {
                                padding: 5px 0;
                                font-weight: bold;
                                font-size: 20px;
                            }
                        }
                    }
                }

                & .col-right {
                    width: calc(100% / 5 * 2);
                    max-height: 500px;

                    & .mini-container {
                        height: calc(100% / 3);
                        display: flex;
                        justify-content: left;
                        align-items: center;
                        border-bottom: 1px solid black;

                        &:hover {
                            scale: 103%;
                            cursor: pointer;
                        }

                        & .div-img-aside {
                            width: 200px;
                            height: 150px;
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
                            font-size: 18px;
                            padding-left: 10px;

                            & span {
                                padding: 0 5px;
                            }

                            & div {
                                padding: 5px 0;
                                font-weight: bold;
                            }
                        }
                    }
                }


            }
        }
    }

    & .featured-posts {
        padding: 30px 0;

        & .top {
            display: flex;
            justify-content: space-between;
            align-items: center;

            & h2 {
                text-transform: uppercase;
                padding: 10px 0;
            }

            & .chevrons i {
                width: 30px;
                height: 30px;
                padding: 10px;
                margin: 0 5px;
                text-align: center;
                color: $secondary-color;
                background-color: $fourth-color;

                border-radius: 50%;

                &:hover {
                    background-color: $main-color;
                    cursor: pointer;
                }
            }
        }


        & .row {
            display: flex;
            justify-content: space-between;

            & .my-col {
                width: calc(100% / 3 - 10px);

                &:hover {
                    scale: 103%;
                    cursor: pointer;
                }

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
                        font-size: 18px;
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
                    font-size: 18px;
                    text-align: center;
                    padding: 20px 0;
                    background-color: $third-color;

                    & .text {
                        padding-top: 10px;
                        margin-bottom: 20px;
                    }

                    & a {
                        padding: 10px 30px;
                        background-color: $main-color;
                        border-radius: 20px;
                        color: $secondary-color;
                        text-decoration: none;

                        &:hover {
                            background-color: $fourth-color;

                        }
                    }
                }
            }
        }
    }

    & .trailers {
        padding: 50px 0;

        & .row {
            display: flex;
            max-height: 500px;
            overflow: hidden;

            & .my-col {
                width: calc(100% / 3 * 2);

                & .trailer-max-container {
                    width: 100%;
                    height: 100%;
                    position: relative;

                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }

                    & .over-icons {
                        font-size: 18px;
                        display: flex;
                        justify-content: space-between;
                        position: absolute;
                        top: 0;
                        left: 0;
                        right: 0;
                        color: $secondary-color;
                        padding: 10px 0;

                        & .left {
                            display: flex;
                            align-items: center;

                            & .tv-icon {
                                width: 40px;
                                height: 40px;
                                margin: 0 10px;

                                & img {
                                    width: 100%;
                                    height: 100%;
                                    object-fit: cover;
                                    border-radius: 50%
                                }
                            }

                            & .title {
                                margin: 0 10px;
                            }
                        }

                        & .right {
                            display: flex;
                            align-items: center;
                            margin: 0 10px;


                            & .watch-later,
                            & .share {
                                text-align: center;
                                margin: 0 10px;
                            }
                        }
                    }

                    & .over-play-icon {
                        position: absolute;
                        top: 50%;
                        left: 50%;
                        transform: translate(-50%);

                        & i {
                            font-size: 60px;
                            color: $main-color;
                        }
                    }

                    & .over-link {
                        font-size: 18px;
                        position: absolute;
                        bottom: 0;
                        left: 0;
                        color: $secondary-color;
                        background-color: $fourth-color;
                        padding: 10px;
                    }
                }
            }

            & .col {
                width: calc(100% / 3 * 1);
                overflow-y: auto;

                .aside-bar {
                    display: flex;
                    align-items: center;
                    padding: 10px;
                    border-bottom: 1px solid black;
                    background-color: $third-color;

                    &:hover {
                        cursor: pointer;
                    }

                    & .number-icon {
                        font-size: 15px;
                        margin-right: 10px;
                        border-radius: 5px;
                        padding: 0 5px;
                        border: 1px solid black;
                        text-align: center
                    }

                    & .active-number {
                        background-color: $main-color;
                        color: $secondary-color;
                    }

                    & .trailer-mini-container {
                        flex-shrink: 0;
                        width: 80px;
                        height: 50px;
                        margin-right: 10px;

                        & img {
                            width: 100%;
                            height: 100%;
                            object-fit: cover;
                            border-radius: 10px;
                        }
                    }

                    & .infos {
                        font-size: 18px;
                    }
                }

                #first-bar {
                    background-color: $fourth-color;
                    color: $secondary-color;

                    & .play-icon {
                        font-size: 30px;
                        margin-right: 20px
                    }

                    & .videos {
                        font-size: 20px;

                        & p:last-child {
                            font-size: 15px;
                        }
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
                    height: width;
                    position: relative;

                    &:hover {
                        & h3 {
                            display: none
                        }

                        & .overlay {
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            cursor: pointer;
                        }
                    }

                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        filter: brightness(0.7);
                    }

                    & h3 {
                        font-size: 30px;
                        text-shadow: 0 0 1px black, 0 0 1px black, 0 0 1px black, 0 0 1px black;
                        color: $secondary-color;
                        font-weight: bold;
                        position: absolute;
                        top: 50%;
                        left: 50%;
                        transform: translate(- 50%, - 50%);
                    }

                    & .overlay {
                        display: none;
                        position: absolute;
                        top: 0;
                        left: 0;
                        right: 0;
                        bottom: 0;
                        background-color: rgba(255, 0, 0, 0.2);

                        & .info {
                            border: 1px solid white;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            flex-direction: column;
                            width: 70%;
                            height: 70%;

                            & p {
                                margin: 10px 0;
                                text-align: center;
                                font-size: 20px;
                                text-transform: uppercase;
                                font-weight: bold;
                                color: $secondary-color;

                                &:first-of-type {
                                    font-size: 30px
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
</style>
