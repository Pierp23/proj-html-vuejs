<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            hdList: {
                home: {
                    text: 'HOME',
                    icon: "fa-solid fa-home fa-lg"
                },
                lifestyle: {
                    text: 'LIFESTYLE',
                    icon: "fa-solid fa-suitcase fa-lg"
                },
                stories: {
                    text: 'STORIES',
                    icon: "fa-solid fa-book-open-reader fa-lg"
                },
                pages: {
                    text: 'PAGES',
                    icon: "fa-solid fa-book fa-lg"
                },
                aboutUs: {
                    text: 'ABOUT US',
                    icon: "fa-solid fa-user fa-lg"
                }
            }
        }
    },
    props: {},
    methods: {

    }
}
</script>

<template>
    <header>
        <!-- HEADER-TOP -->
        <section class="hd-top">
            <div class="container">
                <div class="row">
                    <div class="col-6">
                        <div class="news">
                            News updates
                        </div>
                        <div class="user">
                            <img src="../assets/img/rice-ball-150x150.webp" alt="">
                        </div>
                        <div class="date">
                            05:35 THE _
                        </div>
                    </div>
                    <div class="col-6">
                        <ul>
                            <li class="chevron chevron-sx">
                                <a href="#">
                                    <i class="fa-solid fa-chevron-left"></i>
                                </a>
                            </li>
                            <li class="chevron chevron-dx">
                                <a href="#">
                                    <i class="fa-solid fa-chevron-right"></i>
                                </a>
                            </li>
                            <li>
                                <a href="#">
                                    <i class="fa-brands fa-facebook-f"></i>
                                </a>
                            </li>
                            <li>
                                <a href="#">
                                    <i class="fa-brands fa-twitter"></i>
                                </a>

                            </li>
                            <li>
                                <a href="#">
                                    <i class="fa-brands fa-instagram"></i>
                                </a>

                            </li>
                            <li>
                                <a href="#">
                                    <i class="fa-brands fa-youtube"></i>
                                </a>

                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- HEADER-MIDDLE -->
        <section class="hd-middle">
            <div class="container">
                <div class="row">
                    <div class="col-4">
                        <div class="logo-div">
                            <img src="../assets/img/anime-logo-300x89.webp" alt="">
                        </div>
                    </div>
                    <div class="col-8">
                        <div class="banner">
                            <img src="../assets/img/header-banner.webp" alt="">
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- HEADER-BOTTOM -->
        <section class="hd-bottom">
            <div class="container">
                <div class="row">
                    <div class="col-1">
                        <a href="#">
                            <i class="fa-solid fa-bars fa-lg"></i>
                        </a>
                    </div>
                    <div class="col">
                        <ul v-for="(list, i) in hdList" :key="i">
                            <li>
                                <a href="#">
                                    <i :class="list.icon"></i>
                                    {{ list.text }}
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-1">
                        <a href="#">
                            <i class="fa-solid fa-search fa-lg"></i>
                        </a>
                    </div>
                </div>
            </div>
        </section>
    </header>
</template>

<style lang="scss" scoped>
@use "../assets/scss/main.scss" as *;
@use "../assets/scss/reset.scss" as *;

header {
    .hd-top {
        background-color: $main-color;

        & .container {
            width: 1000px;
            margin: 0 auto;

            & .row {
                display: flex;
                justify-content: space-between;

                & .col-6 {
                    display: flex;
                    align-items: center;
                }

                & .news {
                    display: flex;
                    width: max-content;
                    height: 100%;
                    align-items: center;
                    padding: 10px 20px;
                    font-weight: bold;
                    text-transform: uppercase;
                    color: $secondary-color;
                    background-color: $fourth-color;
                }

                & .user {
                    width: 30px;

                    height: 100%;

                    & img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }
                }

                & .date {
                    display: flex;
                    align-items: center;
                    font-weight: bold;
                    text-transform: uppercase;
                    color: $secondary-color;
                    padding: 10px;
                }

                & ul {
                    list-style: none;
                    padding: 5px;

                    & li {
                        display: inline-block;

                        & a {
                            color: $secondary-color;
                        }
                    }

                    & li:nth-child(3) {
                        margin-left: 50px;
                    }

                    & li:not(.chevron) {
                        width: 20px;
                        height: 20px;
                        border-radius: 50%;
                        text-align: center;
                        line-height: 20px;
                        padding: 0;
                        margin: 0 5px;
                        background-color: $secondary-color;

                        & i:not(.chevron *) {
                            color: $main-color;
                        }

                        &:hover {
                            background-color: $fourth-color;
                            color: $main-color;

                        }
                    }

                    & .chevron {
                        color: $secondary-color;
                        width: 20px;
                        height: 20px;
                        border-radius: 50%;
                        text-align: center;
                        line-height: 20px;

                        &:hover {
                            background-color: $fourth-color;
                            color: $main-color;

                        }
                    }

                    & .chevron-dx {
                        margin-left: 20px;
                        margin-right: 50px;
                    }


                }
            }
        }
    }

    .hd-middle {
        padding: 20px 0;

        & .container {
            width: 1000px;
            margin: 0 auto;

            & .row {
                display: flex;
                justify-content: space-between;

                & .logo-div {
                    width: 200px;

                    & img {
                        width: 100%;
                        object-fit: cover;
                    }
                }
            }
        }
    }

    .hd-bottom {
        padding: 20px 0;

        & .container {
            width: 1000px;
            margin: 0 auto;

            & .row {
                display: flex;
                justify-content: space-between;

                & a {
                    text-decoration: none;
                    color: $fourth-color
                }

                & ul {
                    list-style: none;
                    display: inline-block;

                    & li i {
                        padding: 0 5px;
                    }
                }
            }
        }
    }
}
</style>