<template lang="pug">
    div#app
        div.container
            header.header__section
                nav.header__nav
                    ul.header__list.d-flex.justify-content-around
                        li.header__nav-item
                            a(href="/").header__nav-link.text-decoration-none О себе
                        li.header__nav-item
                            a(href="/").header__nav-link.text-decoration-none Опыт работы
                        li.header__nav-item
                            a(href="/").header__nav-link.text-decoration-none Контакты
                div.header__container-main-heding.d-flex.gap-2
                    img(src="./assets/images/photo.jpg").header__photo
                    h1.header__main-heading Сайт-портфолио <br> Хапилина Альбина
                a(href="/").header__btn-resume.mx-auto.text-decoration-none Посмотреть резюме на HH.ru
            main
                section.about__section
                    h2.h2-style О себе
                    p Меня зовут Альбина. Занимаюсь разработкой и дизайном с 2019 года.
                    p Используемые технологии: <span class="about__text-technology"> HTML5, CSS3, JavaScript, git,  SCSS, JQuery, Bootstrap</span>. Самостоятельно разрабатываю дизайн с помощью Figma, Adobe illustrator.
                    p Опыт работы с <span class="about__text-technology"> Swiper JS</span>, версткой email-писем.
                    p Изучаю новые технологии во frontend-разработке, хочу расти и развиваться в данной сфере.
                    p Более подробное резюме можете просмотреть
                    a(href="/").about__link-resume на сайте hh.ru

                section.work-experience
                    h2.h2-style  Опыт работы
                    div.work-experience__accordion
                        dl(v-for="row in rows").work-experience__accordion-item
                            dt(v-on:click="row.open = !row.open").work-experience__accordion-heading.position-relative {{ row.term }}
                                div.work-experience__accordion-btn.d-flex.justify-content-center.align-items-center.position-absolute
                                    div
                                    div
                            dd(v-if="row.open").work-experience__accordion-description {{ row.details }}

                section.illustrator-experience
                    h2.h2-style  Работы в Adobe Illustrator
                    div slider

                section.contacts
                    h2.h2-style  Контакты
                    p Если вы хотите связаться со мной :
                    p мой почтовый ящик
                    a(href="") albinabist1993@mail.ru
                    p или
                    p оставьте свою почту и выберите цель общения.
                    form
                        input
                        input
                        input
                        button(type="submit") Отправить
            footer © А. С. Хапилина, 2022


    </div>
</template>

<script>

    export default {
        name: 'App',
        data() {
            return {
                rows: {
                    q1: {
                        term: 'СПАО Ингосстрах',
                        details: 'Создала веб-сайты:  https://cosmetology40.ru,  https://solidas.ru,  https://sunny-lucky.ru.\n' +
                            '\n' +
                            'Мной сделана верстка https://finbucket.ru\n' +
                            '\n' +
                            'Техническая поддержка сайта http://prav-avto.ru\n' +
                            '\n',
                        open: false,
                    },
                    q2: {
                        term: 'ФГБОУ Центр информационно-технического обеспечения',
                        details: 'Создала веб-сайты:  https://cosmetology40.ru,  https://solidas.ru,  https://sunny-lucky.ru.\n' +
                            '\n' +
                            'Мной сделана верстка https://finbucket.ru\n' +
                            '\n' +
                            'Техническая поддержка сайта http://prav-avto.ru\n' +
                            '\n',
                        open: false,
                    },
                    q3: {
                        term: 'Фриланс',
                        details: 'Создала веб-сайты:  https://cosmetology40.ru,  https://solidas.ru,  https://sunny-lucky.ru.\n' +
                            '\n' +
                            'Мной сделана верстка https://finbucket.ru\n' +
                            '\n' +
                            'Техническая поддержка сайта http://prav-avto.ru\n' +
                            '\n',
                        open: false,
                    },

                },
            }
        },
    }
</script>

<style lang="scss">
    @import "./assets/scss/general.scss";

    .header__section {
        padding: 70px 0 100px;
    }

    .header__nav {
        margin-bottom: 65px;
    }

    .header__list {
        padding: 0;
        margin: 0;
    }

    .header__nav-link {
        font-weight: 400;
        font-size: 30px;
        padding: 14px 18px;
        background: #222222;
        box-shadow: -13px 13px 26px rgba(14, 14, 14, 0.2), 13px -13px 26px rgba(14, 14, 14, 0.2), -13px -13px 26px rgba(54, 54, 54, 0.9), 13px 13px 33px rgba(14, 14, 14, 0.9), inset 1px 1px 2px rgba(54, 54, 54, 0.3), inset -1px -1px 2px rgba(14, 14, 14, 0.5);
        border-radius: 38px;
        color: $whiteColorText;
    }

    .header__container-main-heding {
        margin-bottom: 30px;
    }

    .header__main-heading {
        color: $yellowColorText;
        font-weight: 400;
        font-size: 59px;
    }

    .header__photo {
        margin-right: 40px;
    }

    .header__btn-resume {
        @include primaryButton;
    }

    /*about*/

    .about__section {
        background: #313234;
        box-shadow: 3px 3px 4px rgba(63, 65, 66, 0.3), -3px -3px 4px rgba(21, 22, 22, 0.5), inset -65px 65px 130px rgba(21, 22, 22, 0.2), inset 65px -65px 130px rgba(21, 22, 22, 0.2), inset -65px -65px 130px rgba(63, 65, 66, 0.9), inset 65px 65px 163px rgba(21, 22, 22, 0.9);
        border-radius: 43px;
        padding: 30px 70px;
        color: $whiteColorText;
        margin-bottom: 90px;
    }

    .about__text-technology, .about__link-resume {
        color: $yellowColorText;
    }

    /*.work-experience*/

    .work-experience__accordion {
        color: white;
    }

    .work-experience__accordion-item {
        padding: 40px 0 0;
        margin: 0;
        border-top: 1px solid $yellowColorText;
        border-bottom: 1px solid $yellowColorText;
    }

    .work-experience__accordion-heading {
        font-weight: 400;
        font-size: 25px;
        margin-bottom: 40px;
    }

    .work-experience__accordion-description {
        font-weight: 400;
        font-size: 20px;
        margin-bottom: 40px;
    }

    .work-experience__accordion-btn {
        @include primaryButton;
        right: 0;
        bottom: -25px;
        width: 85px;
        height: 85px;

        div {
            position: absolute;
            width: 30px;
            height: 2px;
            background-color: $blackColorText;

            &:nth-child(2) {
                transform: rotate(90deg);
            }
        }
    }



</style>
