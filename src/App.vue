<!--
 * @Author: iRuxu
 * @Date: 2022-07-17 01:25:16
 * @LastEditTime: 2022-07-17 19:59:30
 * @Description:
-->
<template>
    <div id="app">
        <Header></Header>
        <Breadcrumb name="剑三茶馆" :slug="slug" :publishEnable="false" :adminEnable="false" :feedbackEnable="true" :crumbEnable="true">
            <Info />
            <publish-gate slot="op-append" />
        </Breadcrumb>
        <LeftSidebar>
            <Nav />
        </LeftSidebar>
        <Main :withoutRight="true">
            <div class="m-main">
                <router-view />
            </div>
            <Footer></Footer>
        </Main>
    </div>
</template>

<script>
import Info from "@/components/Info.vue";
import Nav from "@/components/nav/Nav.vue";
import publishGate from "@/components/publish_gate.vue";
import { getAppIcon, getAppType, getAppID } from "@jx3box/jx3box-common/js/utils";
export default {
    name: "App",
    props: [],
    data: function () {
        return {};
    },
    computed: {
        slug : function (){
            return this.$route.name
        }
    },
    methods: {
        getAppIcon,
    },
    components: {
        Nav,
        "publish-gate": publishGate,
        Info,
    },
    // created: function () {
    //     const regex = /\/bbs\/?#\/?(\w+?)\/(\d+)/
    //     location.pathname.match(regex) && (location.href = location.pathname.replace(regex, '/$1/$2'))
    // },
};
</script>

<style lang="less">
    @import "./assets/css/app.less";
</style>
