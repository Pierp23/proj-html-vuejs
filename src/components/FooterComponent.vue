<script>
export default {
    name: "FooterComponent",
    data() {
        return {
            ftList: {
                getStarted: {
                    title: 'Get Started',
                    list: ['Resources', 'Tutorials', 'Examples', 'Docs']
                },
                about: {
                    title: 'About',
                    list: ['Stories', 'Community', 'Blog', 'Brand Assets']
                },
                features: {
                    title: 'Features',
                    list: ['Overview', 'Design', 'Code', 'Collaborate']
                },
                quickLinks: {
                    title: 'Quick Links',
                    list: ['Stories', 'Community', 'Blog', 'Brand Assets']
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
    <footer>


        <section class="container">
            <div class="ft-top row">
                <div class="my-col-3-3">
                    <div class="row">
                        <div class="col-3" v-for="(list, i) in ftList" :key="i">
                            <h3>
                                {{ list.title }}
                            </h3>
                            <ul>
                                <li v-for="(li, i) in ftList[i].list" :key="i">
                                    <a href="#">
                                        {{ li }}
                                    </a>

                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="my-col-1-3 form-div">
                    <h3>Subscribe to newsletter</h3>
                    <form action="">
                        <input type="email" placeholder="   Email">
                        <button type="submit">SUBSCRIBE</button>
                    </form>


                </div>
            </div>
            <hr>
            <div class="ft-bottom">
                <div class="logo">
                    <img src="../assets/img/anime-whitelogo-300x89.png" alt="logo">
                </div>
                <p>
                    &copy;Anime Tech, Theme by HaisnainDEV
                </p>
            </div>

        </section>
    </footer>
</template>

<style lang="scss" scoped>
@use "../assets/scss/main.scss" as *;
@use "../assets/scss/reset.scss" as *;

footer {
    background-color: $main-color;

    .container {
        width: 1000px;
        margin: 0 auto;
        padding-top: 30px;


        & .ft-top {
            display: flex;
            justify-content: space-between;
            padding-bottom: 50px;

            & .my-col-3-3 {
                width: calc(100% / 3) * 2;

                & .row {
                    display: flex;
                    justify-content: space-between;
                    align-items: center;

                    & h3 {
                        text-transform: uppercase;
                        color: $secondary-color;
                    }

                    & ul {
                        list-style: none;
                        padding: 0;
                        margin-top: 10px;

                        & li {
                            padding: 5px 0;

                            & a {
                                text-decoration: none;
                                color: $secondary-color;

                                &:hover {
                                    color: $fourth-color;
                                }
                            }


                        }
                    }
                }
            }

            & .my-col-1-3 {
                width: calc(100% / 3) * 1;
            }

            & .form-div {
                margin-left: 50px;

                h3 {
                    text-transform: uppercase;
                    color: $secondary-color;
                }

                input {
                    border-radius: 5px;
                    width: 100%;
                    padding: 10px 0;
                    margin: 5px 0;
                }

                button {
                    color: $secondary-color;
                    background-color: $fourth-color;
                    display: block;
                    border-radius: 5px;
                    width: 100%;
                    padding: 10px 0;
                    margin-bottom: 5px;

                    &:hover {
                        background-color: $secondary-color;
                        color: $main-color;
                        cursor: pointer;
                    }
                }


            }
        }

        & .ft-bottom {
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: $secondary-color;
            padding: 10px 0;

            & .logo {
                width: 200px;

                & img {
                    width: 100%;
                    object-fit: cover;
                }
            }
        }
    }
}
</style>