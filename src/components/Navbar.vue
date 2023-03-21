<template>

    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <a class="navbar-brand" href="#">My Vue</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav"
            aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <a class="nav-link" :class="{ active: activePage === index }" aria-current="page" :href="page.link.url"
                        :title="`this link goes to ${page.link.text} page`" @click.prevent="navLinkClick(index)">{{
                            page.link.text }}</a>
                </li>
            </ul>
            <form class="d-flex ml-auto">
                <button class="btn btn-primary" @click.prevent="changeTheme()"> Change Theme
                </button>
            </form>
        </div>
    </nav>

</template>

<script>
export default {
    props: ['pages', 'active-page', 'navLinkClick'],
     
    data() {
        return {
            theme: 'dark'
        }
    },
    methods: {
        changeTheme() {
            let theme = 'light';
            if (this.theme == 'light') {
                theme = 'dark';
            }
            this.theme = theme;
        }
    }
}

</script>