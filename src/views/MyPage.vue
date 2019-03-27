<template>
<transition name="fade">
    <div class="container" v-show="seen">
        <div class="wrapper">
            <div class="user__container">
                <img class="edit" src="../img/edit.svg" alt="edit" @click="foo">
                <img src="../img/avatar.png" alt="avatar">
                <p>{{ userFirstName }} {{ userLastName }}</p>
                <p class="link" @click="some">{{ link }}</p>

                <div class="stats">
                    <span><span class="number">{{ folowers }}</span> Подписчики</span>
                    <span><span class="number">{{ folow }}</span> Подписки</span>
                    <span><span class="number">{{ rate }}</span> Рейтинг</span>
                </div>

                <div class="links">
                    <a href="#"><img src="../img/google.svg" alt="link"></a>
                    <a href="#"><img src="../img/facebook.svg" alt="link"></a>
                    <a href="#"><img src="../img/instagram.svg" alt="link"></a>
                </div>
            </div>

            <div class="somethingNew">
                <input type="text" placeholder="Что интересного сегодня?" @keyup.enter="bar" v-model="news">
            </div>

            <div class="chat">
                <div class="head">
                    <img src="../img/chat-logo.svg" alt="chat">
                </div>

                <div class="messageWrapper">
                    <div class="comment">
                        <div class="firstRow">
                            <div class="leftCOntent">
                                <img src="../img/mini-avatar.svg" alt="ava">
                                <p class="name">Шакира Арзимановна</p>
                            </div>
                            <div class="rightContent">
                                <p class="timeAgo">только что</p>
                            </div>
                        </div>
                        <div class="messageRow">
                                <p> привет всем))) меня закинуло в чат топ 
                                    100) я теперь с вами кек пук чо аллоха 
                                    это третья строка здарова бать...
                                </p>
                        </div>
                        <div class="linkOnGroup">
                            <a href="#">[Гейминг] Топ-100 -></a>
                        </div>
                    </div>
                </div>

                <div class="messageWrapper">
                    <div class="comment">
                        <div class="firstRow">
                            <div class="leftCOntent">
                                <img src="../img/mini-avatar2.svg" alt="ava">
                                <p class="name">МакДрейк Младенец</p>
                            </div>
                            <div class="rightContent">
                                <p class="timeAgo">22 сек назад</p>
                            </div>
                        </div>
                        <div class="messageRow">
                                <p> 
                                    коллеги !!! мой рейтинг упал всем привет !
                                </p>
                        </div>
                        <div class="linkOnGroup">
                            <a href="#">[Социальный] Топ-500 -></a>
                        </div>
                    </div>
                </div>

                <div class="messageWrapper">
                    <div class="comment">
                        <div class="firstRow">
                            <div class="leftCOntent">
                                <img src="../img/mini-avatar3.svg" alt="ava">
                                <p class="name">Антон Гудрон</p>
                            </div>
                            <div class="rightContent">
                                <p class="timeAgo">минуту назад</p>
                            </div>
                        </div>
                        <div class="messageRow">
                                <p>
                                    е бой, бой с самим собой е бой е бой е бой е йбоооооойо
                                </p>
                        </div>
                        <div class="linkOnGroup">
                            <a href="#">[Гейминг] Топ-100 -></a>
                        </div>
                    </div>
                </div>

                <div class="chatFooter">
                    <p>Все сообщения</p>
                </div>
            </div>
        </div>

        <div class="wrapper2">
            <div class="contain-down">
                <div class="infoProgress">
                    <div class="wrapProgress">
                        <p>Вы заполнили профиль на 70%</p>
                        <div class="progressBar">
                            <div class="fullProgress">
                            </div>
                        </div>
                        <a href="#">Заполнить еще -></a>
                    </div>
                </div>

                <div class="themes">
                    <div class="theme">
                        <div class="leftCnt">
                            <img src="../img/pokemon-colors.svg" alt="image">
                            <p>Спорт -></p>
                        </div>
                        <div class="rightCnt">
                            <p class="score">18</p>
                        </div>
                    </div>

                    <div class="theme active">
                        <div class="leftCnt">
                            <img src="../img/pokemon-white.svg" alt="image">
                            <p>Гейминг -></p>
                        </div>
                        <div class="rightCnt">
                            <p class="score">941</p>
                        </div>
                    </div>

                    <div class="theme">
                        <div class="leftCnt">
                            <img src="../img/pokemon-colors.svg" alt="image">
                            <p>Социальный -></p>
                        </div>
                        <div class="rightCnt">
                            <p class="score">20</p>
                        </div>
                    </div>

                    <div class="theme">
                        <div class="leftCnt">
                            <img src="../img/education.svg" alt="image">
                            <p>Образование -></p>
                        </div>
                        <div class="rightCnt">
                            <p class="score">102</p>
                        </div>
                    </div>
                    <div class="buttons">
                        <div class="btn">
                            <p>Добавить еще</p> <img src="../img/plus-light.svg" alt="icon">
                        </div>
                        <div class="btn2">
                            <p>Смотреть все</p> <img src="../img/arrows-4.svg" alt="icon">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</transition>
</template>

<script>
export default {
    data() {
        return {
            seen: false,
            userFirstName: 'Катя',
            userLastName: 'Морозова',
            link: '@morozovakate',
            folowers: '3к',
            folow: '101',
            rate: 28,
            news: ''
        }
    },
    methods: {
        some() {
            alert('Допустим скопировали ссылку в буфер')
        },
        foo() {
            alert('Открыли модалку с редактированием профиля')
        },
        bar() {
            if (this.news === '' || this.news === ' ') {
                alert('Нужно что-то написать')
            } else {
                alert('Добавили вот это в новости -> ' + this.news)
                this.news = ''
            }
        }
    },
    mounted() {
        this.seen = true;
    }
}
</script>

<style scoped>
/* Main container */
.wrapper {
    max-width: 1140px;
    margin: 0 auto;
    display: flex;
    box-sizing: border-box;
    justify-content: space-between;
}

/* User container */
.user__container {
    width: 360px;
    height: 400px;
    border: 1px solid #ECEBED;
    margin-top: 30px;
    box-shadow: 0px 7px 20px rgba(0, 0, 0, 0.07);
    border-radius: 10px;
    transition: all .5s;
    position: absolute;
    padding-bottom: 16px;
}

.edit {
    position: absolute;
    right: 30px;
    top: -20px;
    cursor: pointer;
    width: 10px;
    transition: all .5s;
}

.edit:hover {
    width: 12px;
}

.user__container:hover {
    border: 1px solid rgba(92, 45, 174, 0.283);
}

.user__container img {
    margin-top: 40px;
}

.user__container p {
    font-size: 17px;
    line-height: 22px;
    font-weight: 500;
    text-align: center;
    color: #1E1923;
    margin-top: 20px;
    margin-bottom: 0px;
}

.user__container .link {
    font-size: 15px;
    line-height: 20px;
    color: #D0C9D6;
    display: inline;
    cursor: pointer;
}

.stats {
    width: 300px;
    margin: 0 auto;
    border-top: 1px solid #ECEBED;
    border-bottom: 1px solid #ECEBED;
    padding: 20px 0;
    margin-top: 20px;
    margin-bottom: 0;
}

.stats span {
    font-size: 12px;
    line-height: 15px;
    color: #D0C9D6;
    margin-right: 20px;
}

.stats span:last-child {
    margin-right: 0;
}

.stats .number {
    color: #1E1923;
}

.link {
    display: flex;
    align-items: center;
}

.links img {
    margin-top: 14px;
}

.links a {
    margin-right: 27px;
}

.links a:last-child {
    margin-right: 0;
}

/* New's ipnut */

.somethingNew input {
    background: url(../img/plus.svg) no-repeat left padding-box;
    background-position: 9px;
    padding-left: 30px;
    padding-top: 14px;
    padding-bottom: 14px;
    outline: none;
    height: 20px;
    width: 440px;
    border: none;
    box-shadow: 0px 7px 64px rgba(0, 0, 0, 0.075);
    border-radius: 6px;
    font-size: 15px;
    line-height: 20px;
    margin-top: 30px;
    margin-left: 380px;
    margin-right: 20px;
}

/* Chat */

.chat {
    margin-top: 30px;
}

.head {
    border: 1px solid #ECEBED;
    width: 300px;
    border-radius: 10px 10px 0px 0px;
    text-align: left;
    padding-top: 16px;
    padding-bottom: 13px;
    padding-left: 16px;
    display: flex;
}

.messageWrapper {
    border: 1px solid #ECEBED;
    width: 300px;
    border-top: none;
    padding-top: 10px;
    padding-left: 16px;
}

.firstRow {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-right: 16px;
}

.leftCOntent {
    display: flex;
}

.name {
    margin-left: 8px;
    font-size: 12px;
    line-height: 16px;
    color: #1E1923;
}

.timeAgo {
    font-size: 11px;
    line-height: 13px;
    text-align: right;
    color: #D0C9D6;
    margin-left: 55px;
    text-align: right;
}

.messageRow {
    width: 268px;
}

.messageRow p {
    font-size: 12px;
    line-height: 16px;
    text-align: left;
    padding-right: 16px;
    margin-top: 0;
}

.linkOnGroup {
    text-align: left;
    margin-top: -3px;
    margin-bottom: 10px;
}

.linkOnGroup a {
    font-size: 13px;
    line-height: 18px;
    text-decoration: none;
    color: #8562C2;
}

.linkOnGroup a:hover {
    border-bottom: 1px solid #8562C2;
}

.chatFooter {
    border: 1px solid #ECEBED;
    border-top: none;
    width: 300px;
    border-radius: 0px 0px 10px 10px;
    text-align: left;
    padding-top: 16px;
    padding-bottom: 16px;
    padding-left: 16px;
    display: flex;
    text-align: center;
}

.chatFooter p {
    font-size: 15px;
    line-height: 20px;
    margin: 0;
    padding: 0;
    color: #D0C9D6;
    margin: 0 auto;
    cursor: pointer;
}

/* wrapper2 infoProgress */

.wrapper2 {
    margin-top: -70px;
}

.contain-down {
    max-width: 1140px;
    margin: 0 auto;
}

.infoProgress {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    text-align: center;
}

.infoProgress p{
    font-size: 11px;
    line-height: 13px;
    text-align: center;
    color: #5C2DAE;
    margin-bottom: 6px;
}

.infoProgress a {
    font-size: 15px;
    line-height: 20px;
    text-align: right;
    color: #D0C9D6;
    text-decoration: none;
    margin-top: 10px;
}

.infoProgress .wrapProgress {
    margin-left: 65px;
}

.progressBar {
    width: 230px;
    height: 8px;
    background-color: #D6CAEA;
    border-radius: 4px;
}

.fullProgress {
    width: 138px;
    height: 8px;
    border-radius: 4px;
    background: linear-gradient(183.32deg, #9265E1 0%, #5C2DAE 100%);
}

.themes {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-top: 40px;
}

.theme {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 320px;
    height: 46px;
    text-align: left;
    border: 2px solid #ECEBED;
    border-radius: 10px;
    padding-left: 13px;
    cursor: pointer;
    margin-top: 16px;
    box-shadow: 0px 7px 20px rgba(0, 0, 0, 0.07);
}

.theme:hover:nth-child(2) {
    cursor: default;
}

.theme:nth-child(2) {
    border: none;
    background: linear-gradient(to right, #575cff 0%,#912ff4 100%);
}

.theme:nth-child(2) p {
    color: #fff;
}

.theme:first-child {
    margin-top: 0;
}

.theme:hover {
    background-color: #ECEBED;
}

.theme p {
    font-size: 15px;
    line-height: 20px;
    color: #3F3356;
    margin-left: 13px;
}

.leftCnt {
    display: flex;
}

.rightCnt .score {
    font-size: 22px;
    line-height: 20px;
    color: #D0C9D6;
    margin-right: 16px;
}

.buttons {
    display: flex;
    width: 330px;
    justify-content: space-between;
    margin-bottom: 5em;
}

.btn, .btn2 {
    display: flex;
    cursor: pointer;
}

.btn p, .btn2 p {
    margin-right: 11px;
    font-size: 15px;
    line-height: 20px;
    color: #D0C9D6;
}

/* Fade Effect */
.fade-enter-active, .fade-leave-active {
  transition: opacity 2s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
