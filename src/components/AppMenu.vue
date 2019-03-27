<template>
    <div class="wrapper">
        <div class="container">
            <div class="menu">
                <ul v-if="userAuth">
                    <li>
                        <router-link to="/mypage">
                        <img src="../img/page-logo.png" alt="icon">Моя Страница</router-link>
                    </li>
                    <li>
                        <router-link to="/lent">
                        <img src="../img/lent-logo.png" alt="icon">Лента</router-link>
                    </li>
                    <li>
                        <router-link to="/message">
                        <img src="../img/message-logo.png" alt="icon">Сообщения</router-link>
                    </li>
                </ul>
                <ul v-else>
                    <li>
                        <router-link to="/lent"> Зарегистрироваться</router-link>
                    </li>
                    <li>
                        <router-link to="/message">Войти</router-link>
                    </li>
                </ul>
            </div>

            <div class="logo" @click="goToMain">
                <img src="../img/logo.svg" alt="">
            </div>

            <div class="search">
                <input type="text" placeholder="Search...">
            </div>

            <div class="profile" @click="bar">
                <span>{{ userFirstName }}</span>
                <img class="avatar" src="../img/avatar.png" alt="avatar">
                <img src="../img/arrow-down.png" alt="arrow">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            userAuth: true,
            userFirstName: 'Катя',
            userLastName: 'Морозова'
        }
    },
    methods: {
        bar() {
            alert('Тут должно было что-то выехать :)')
        },
        goToMain() {
            this.$router.push('/')
        }
    }
}
</script>

<style scoped>
/* Main container's */
.wrapper {
    border-bottom: 1px solid #ECEBED;
}

.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1210px;
    margin: 0 auto;
}

/* Menu */
ul {
    list-style: none;
    display: flex;
    justify-content: center;
    margin: 15px 0;
}

a {
    text-decoration: none;
    color: #3F3356;
    margin-right: 14px;
    display: flex;
    align-items: center;
    font-size: 15px;
    line-height: 20px;
}

a img {
    margin-right: 13px;
}

.router-link-exact-active {
    color: #5C2DAE;
}

/* Logo */

.logo {
    margin-left: -100px;
    cursor: pointer;
}

/* Search */

.search input {
    border: 1px solid #ECEBED;
    border-radius: 6px;
    padding: 9px 0px;
    background: url(../img/search.png) no-repeat left padding-box;
    background-position: 9px;
    padding-left: 35px;
    color: #1E1923;
    margin-left: -200px;
    font-size: 15px;
    line-height: 20px;
    outline: none;
    transition: all .5s;
}

.search input:focus {
    border: 1px solid rgba(92, 45, 174, 0.461);
}

/* Profile */
.profile {
    display: flex;
    align-items: center;
    font-size: 13px;
    line-height: 18px;
}

.profile {
    cursor: pointer;
}

.avatar{
    width: 34px;
    margin: 0 10px;
}
</style>
