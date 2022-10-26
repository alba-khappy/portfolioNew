<template lang="pug">
    div#app
        div.container
            header
                nav.header__nav
                    ul.header__list
                        li.header__nav-item
                            a(href="/") О себе
                        li.header__nav-item
                            a(href="/") Опыт работы
                        li.header__nav-item
                            a(href="/") Контакты
                div.header__main-heding
                    img(src="logo.png", alt="photo")
                    h1 Сайт-портфолио <br> Хапилиной Альбины
                a(href="/") Посмотреть резюме на HH.ru
            main
                section.about
                    h2 О себе
                    p Меня зовут Альбина. Занимаюсь разработкой и дизайном с 2019 года.
                    p Используемые технологии: HTML5, CSS3, JavaScript, git,  SCSS, JQuery, Bootstrap. Самостоятельно разрабатываю дизайн с помощью Figma, Adobe illustrator.
                    p Опыт работы с Swiper JS, версткой email-писем.
                    p Изучаю новые технологии во frontend-разработке, хочу расти и развиваться в данной сфере.
                    p Более подробное резюме можете просмотреть
                    a(href="/") на сайте hh.ru

                section.work-experience
                    h2 Опыт работы
                    div ghghgh

                section.illustrator-experience
                    h2 Работы в Adobe Illustrator
                    div slider

                section.contacts
                    h2 Контакты
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
    }
</script>

<style lang="scss">
    @import "./assets/scss/general.scss";

</style>
