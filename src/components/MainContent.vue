<template>
    <div>
        <div class ="main-content" v-bind:class="{'fix': this.isMobileMenuToggled}">
            <div class ="bubble" v-bind:class="{'show': this.isMobileMenuToggled}"></div>
            <div class = "menu-button" @click="toggleMenu">Menu</div>   
            <h1>This is the title</h1>
            <div>
                This is the content
            </div>
        </div>

        <div class="side-menu" v-bind:class="{'show': this.isMobileMenuToggled}">
            <div class = "menu-button" @click="toggleMenu">X</div>
            <div class="menu-container">
                <div class="menu-item">
                    <img src="@/assets/sample.svg">
                    <div class="text">
                        Sample Text
                    </div>
                </div>
                <div class="menu-item">
                    <img src="@/assets/sample.svg">
                    <div class="text">
                        Sample Text
                    </div>
                </div>
                <div class="menu-item">
                    <img src="@/assets/sample.svg">
                    <div class="text">
                        Sample Text
                    </div>
                </div>
                <div class="menu-item">
                    <img src="@/assets/sample.svg">
                    <div class="text">
                        Sample Text
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "MainContent",
    props: {
        msg: String
    },
    data() {
        return {
            isMobileMenuToggled: true,
        };
    },
    methods: {
        toggleMenu() {
            this.isMobileMenuToggled = !this.isMobileMenuToggled;
        }
    }
};
</script>

<style lang="scss">
$primary: #17BEBB;
$secondary: #FFC914;

.main-content{
    background: $primary;
    width: 100%;
    min-height: 100vh;
    overflow: hidden;
    &.fix{
        position: fixed;
    }
}

.menu-button{
    text-align: right;
    padding: 2rem;
}

.bubble{
    background: $secondary;
    width: 1000px;
    height: 1000px;
    border-radius: 50%;
    //-webkit-transform: scale(0.05);
    //transform: scale(0.05);
    position: absolute;
    top: -459px;
    right: -448px;
    animation: bubble-expand-rev 1s 1 ease-in-out forwards;
    &.show{
        animation: bubble-expand 3s 1 cubic-bezier(.15,1.3,.74,1.07) forwards;
    }
}

.side-menu {
    width: 100%;
    height: 100vh;
    position: absolute;
    top: 0;
    animation: hide-menu-items 0.5s linear  forwards;
    .menu-container {
        .menu-item {
            //background: $secondary;
            background: rgba(255,255,255,0.2);
            margin-bottom: 3px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 5px;
            padding: 1rem;
            img {
                width: 75px;
                height: 75px;
            }
            .text {
                font-size: 2rem;
            }
        }
    }
    &.show{
        animation: show-menu-items 1s linear forwards;
    }

    @keyframes example {
        0% {
            //transform: scale(0.1) translateX(500vw) translateY(-500vh) rotate(-90deg)
            transform: scale(0.1);
        }
        70% {
            transform: scale(0.5);
            //transform: scale(1.5) translateX(250vw) translateY(-250vh) rotate(-90deg)
        }
        100% {
            transform: scale(1);
            ///transform: scale(1.5) translateX(0) translateY(0) rotate(0)
        }
    }

    @keyframes show-menu-items {
        0%{
            opacity: 0;
        }
        50%{
            opacity: 0;
        }
        100%{
            opacity: 1;
        }
    }

    @keyframes hide-menu-items {
        0%{
            opacity: 1;
            //visibility: visible;
        }
        100%{
            opacity: 0;
            //visibility: hidden;
        }
    }

    @keyframes bubble-expand {
        0%{
            transform: scale(0.01);
        }
        100%{
            transform: scale(2.5);
        }
    }
    @keyframes bubble-expand-rev {
        0%{
            transform: scale(2.5);
            //opacity: 1;
            visibility: visible
        }
        100%{
            transform: scale(0.01);
            //opacity: 0;
            visibility: hidden;
        }
    }

}
</style>
