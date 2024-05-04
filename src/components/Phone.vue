<template lang="">
    <div class="phone">
        <div :class="{ pressAnimation: pressed}" class="power-button" @click="togglePower"></div>
        <div class="volume-up-button"></div>
        <div class="volume-down-button"></div>
        <div class="screen">
            <video autoplay loop muted v-show="isOn">
                <source src="/imatedemo.mp4" type="video/mp4">
            </video>
        </div>
        <div class="camera"></div>
    </div>
</template>
<script>
export default {
    name: 'Phone',
    data() {
        return {
            isOn: true,
            pressed: false
        }
    },
    methods: {
        togglePower() {
            this.isOn = !this.isOn;
            this.pressed = true;
            setTimeout(() => {
                this.pressed = false
            }, 500)
        }
    },
}
</script>
<style lang="css">
    :root {
        --button-width: 6px;
        --power-button-height: 50px;
        --power-button-top-offset: 90px;
        --volume-button-height: 80px;
    }
    .phone {
        background-color: #0a0a0a;
        padding: 15px;
        border-radius: 40px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        width: calc(1080px / 3.5);
        margin: 0 auto;
        height: calc(2400px / 3.5);
        /* 1080 x 2400 pixels, 20:9 ratio (~395 ppi density) */
        color: white;
        border: 7px solid gray;
        position: relative;
        animation: hover 4s infinite ease-in-out;
    }

    .power-button {
        width: var(--button-width);
        height: var(--power-button-height);
        border-radius: 2px 0 0 2px;
        background-color: rgb(59, 58, 58);
        position: absolute;
        top: var(--power-button-top-offset);
        left: calc(-1 * (var(--button-width) + 7px));
    }

    .volume-up-button {
        width: var(--button-width);
        height: var(--volume-button-height);
        border-radius: 2px 0 0 2px;
        background-color: rgb(59, 58, 58);
        position: absolute;
        top: calc(var(--power-button-top-offset) + var(--power-button-height) + 30px);
        left: calc(-1 * (var(--button-width) + 7px));
    }

    .volume-down-button {
        width: var(--button-width);
        height: var(--volume-button-height);
        border-radius: 2px 0 0 2px;
        background-color: rgb(59, 58, 58);
        position: absolute;
        top: calc(var(--power-button-top-offset) + var(--power-button-height) + var(--volume-button-height) + 40px);
        left: calc(-1 * (var(--button-width) + 7px));
    }

    .screen {
        background-color: black;
        width: calc((1080px / 3.5));
        height: calc((2400px / 3.5));
        /* 1080 x 2400 pixels, 20:9 ratio (~395 ppi density) */
        border-radius: 20px;
    }

    video {
        width: 100% !important;
        height: 100% !important;
        object-fit: cover;
        border-radius: 20px;
    }
    
    .camera {
        width: 150px;
        height: 20px;
        background-color: #0a0a0a;
        border-radius: 0 0 10px 10px;
        position: absolute;
        top: 10px;
        right: 50%;
        transform: translateX(50%);
    }

    .pressAnimation {
        animation: press 0.5s ease infinite;
    }

    @keyframes press {
        0% {
            transform: scaleX(1);
        }
        50% {
            transform: scaleX(0.2);
        }
        100% {
            transform: scaleX(1);
        }
    }

    @keyframes hover {
        0% {
            transform: translateY(0);
        }
        50% {
            transform: translateY(-10px);
        }
        100% {
            transform: translateY(0);
        }
    }
</style>