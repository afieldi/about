<template>
    <nav id="main-nav" class="navbar navbar-expand-lg navbar-dark bg-danger sticky-top" v-bind:style="{top: topOffset + 'px'}">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li v-bind:class="['nav-item', current=='profile'?'active':'']">
                    <a class="nav-link" v-on:click="scrollTo('profile')">Profile</a>
                </li>
                <li v-bind:class="['nav-item', current=='experience'?'active':'']">
                    <a class="nav-link" v-on:click="scrollTo('experience')">Experience</a>
                </li>
                <li v-bind:class="['nav-item', current=='skills'?'active':'']">
                    <a class="nav-link" v-on:click="scrollTo('skills')">Skills</a>
                </li>
                <li v-bind:class="['nav-item', current=='projects'?'active':'']">
                    <a class="nav-link" v-on:click="scrollTo('projects')">Projects</a>
                </li>
                <!-- <li v-bind:class="['nav-item', current=='contact'?'active':'']">
                    <a class="nav-link" v-on:click="scrollTo('contact')">Contact</a>
                </li> -->
                <li class="nav-item">
                    <a class="nav-link" v-on:click="$emit('openresume')">Resume</a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
export default {
    props: ["current"],
    data: function ( ) { 
        return { 
            topOffset: 0,
            lastY: -1,
            maxOffset: 0,
        }
    },
    created: function ( ) {
        window.addEventListener ( 'scroll', this.scrollNav );
    },
    destroyed: function ( ) {
        window.removeEventListener ( 'scroll', this.scrollNav );
    },
    mounted: function ( ) {
        this.maxOffset = document.getElementById('main-nav').offsetHeight * -1;
    },
    methods: {
        scrollTo: function ( sectionId ) {
            try {
                $('html,body').animate({
                scrollTop: $(`#${sectionId}`).offset().top},
                'slow');
                this.topOffset = this.maxOffset;
            } catch (error) {
                
            }
        },
        scrollNav: function ( event ) {
            var curY = window.scrollY;
            if ( this.lastY < 0 ) {
                this.lastY = curY;
            }
            var delta = this.lastY - curY;
            if ( delta < 0 ) {
                if ( this.topOffset > this.maxOffset ) {
                    this.topOffset += delta * .15
                }
            }
            else if ( delta > 0 ) {
                if ( this.topOffset < 0 ) {
                    this.topOffset += delta
                }
                else if ( this.topOffset > 0) {
                    this.topOffset = 0
                }
            }

            this.lastY = curY;
        }
    }
}
</script>

<style>
.nav-link:hover {
    cursor: pointer;
}
@media (min-width: 768px) {
    .navbar {
        position: sticky;
    }

    .navbar .navbar-nav {
        margin-left: 50%;
        transform: translateX(-50%);
        text-align: center;
    }

    .navbar .navbar-collapse {
        text-align: center;
    }
}
@media (max-width: 768px) {
    .navbar-toggler {
        transform: translateX(-50%);
        left: 48vw;
        position: relative;
    }
}
</style>