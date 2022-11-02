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

                section
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
                    div.wrapper
                        split-carousel(v-bind="option")
                            h3(slot='left-arrow').illustrator-experience__swiper-btn.illustrator-experience__swiper-btn--left
                            split-carousel-item(v-for="illustration in illustrations").illustrator-experience__image-container
                                img(:src="require(`./assets/images/${illustration}`)").illustrator-experience__image
                            h3(slot='right-arrow').illustrator-experience__swiper-btn




                section.contacts.d-flex.flex-column.align-items-center
                    h2.h2-style  Контакты
                    p.contacts__text Если вы хотите связаться со мной :
                    p.contacts__text мой почтовый ящик
                    a(href="").contacts__link albinabist1993@mail.ru
                    p.contacts__text или
                    p.contacts__text оставьте свою почту и выберите цель общения.
                    form.contacts__form.d-flex.flex-column.align-items-center
                        input.contacts__input
                        input.contacts__input
                        div.contacts__dropdown
                            b-dropdown(id="dropdown-left", text='Выберите цель', no-caret).contacts__dropdown-heading
                                b-dropdown-item(href='#').contacts__item Предложение вакансии
                                b-dropdown-item(href='#').contacts__item Заказ landing page
                                b-dropdown-item(href='#').contacts__item Создание дизайна сайта
                                b-dropdown-item(href='#').contacts__item  Другой вопрос


                        button(type="submit").contacts__btn-submit Отправить
            footer © А. С. Хапилина, 2022


    </div>
</template>

<script>
    import { SplitCarousel, SplitCarouselItem } from "vue-split-carousel";
    const defaultConfig = {
        displayAmount: 4,
        autoplay: true,
        speed: 300,
        interval: 3000,
        loop: true,
        height: 220,
        itemWidth: 215,
        pauseOnHover: true,
        timingFunction: "ease",
        arrowVisible: "enable",
    };

    export default {
        name: 'App',
        components: {
            SplitCarousel,
            SplitCarouselItem
        },
        data() {
            return {
                option: { ...defaultConfig },
                illustrations: ["il-1.png", "il-2.png", "il-3.png","il-4.png", "il-5.png", "il-6.png"],
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
        border-top: 1px solid transparent;
        border-image: url(./assets/images/accordion-border.svg) 30 stretch;

        &:nth-child(3) {
            border-bottom: 1px solid transparent;
        }
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

    /*illustrator-experience*/

    .illustrator-experience__image-container:hover {
        transform: scale(1.1);
    }

    .illustrator-experience__image {
        width: 215px;
        height: 220px;
        filter: grayscale(1);
        transition: .3s ease-in-out;
    }

    .illustrator-experience__image:hover {
        filter: grayscale(0);
    }

    /*swiper*/

    .wrapper {
        width: 100%;
        margin: 0 auto;
    }

    .swiper-slide{
        display: flex;
        justify-content: center;
        flex-direction: column;
    }


    .illustrator-experience__swiper-btn {
        background: transparent url("assets/images/arrow.svg") no-repeat center;
        width: 35px;
        height: 60px;
    }

    .illustrator-experience__swiper-btn--left {
        transform: rotate(180deg);
    }

    /*contacts*/

    .contacts__text {
        color: $whiteColorText;
        font-size: 30px;
    }

    .contacts__link {
        color: $yellowColorText;
        font-size: 30px;
    }

    .contacts__input {
        width: 100%;
        max-width: 680px;
        background: #D9D9D9;
        box-shadow: 1px 1px 2px rgba(255, 255, 255, 0.3), -1px -1px 2px rgba(135, 135, 135, 0.5), inset -12px 12px 24px rgba(135, 135, 135, 0.2), inset 12px -12px 24px rgba(135, 135, 135, 0.2), inset -12px -12px 24px rgba(255, 255, 255, 0.9), inset 12px 12px 30px rgba(135, 135, 135, 0.9);
        border-radius: 30px;
        padding: 5px 20px;
        color: $blackColorText;
        margin-bottom: 30px;
        border: 0;
    }

    .contacts__btn-submit {
        @include primaryButton;
    }

    .contacts__dropdown {
        margin-bottom: 100px;
    }

    .dropdown-left__BV_toggle_.btn-secondary {
        background: #D9D9D9;
    }

    .dropdown-menu button {
        background: #D9D9D9;
    }

    .dropdown-menu {
        background: #D9D9D9;
        box-shadow: 1px 1px 2px rgba(255, 255, 255, 0.3), -1px -1px 2px rgba(135, 135, 135, 0.5), inset -12px 12px 24px rgba(135, 135, 135, 0.2), inset 12px -12px 24px rgba(135, 135, 135, 0.2), inset -12px -12px 24px rgba(255, 255, 255, 0.9), inset 12px 12px 30px rgba(135, 135, 135, 0.9);
        border-radius: 30px;
    }

    .contacts__dropdown-heading {
        max-width: 680px;
        min-width: 220px;
        border-radius: 30px;
    }

    #dropdown-left button {
        box-shadow: 1px 1px 2px rgba(255, 255, 255, 0.3), -1px -1px 2px rgba(135, 135, 135, 0.5), inset -12px 12px 24px rgba(135, 135, 135, 0.2), inset 12px -12px 24px rgba(135, 135, 135, 0.2), inset -12px -12px 24px rgba(255, 255, 255, 0.9), inset 12px 12px 30px rgba(135, 135, 135, 0.9);
        border-radius: 30px;
        color: $blackColorText;
    }

    div div#dropdown-left ul.dropdown-menu.show {
        border-radius: 30px;
    }

    .contacts__item a {
        padding: 10px 14px;
        text-align: center;
    }


</style>
