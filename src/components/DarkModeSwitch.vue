<template>
    <div class="toggleWrapper">
        <input type="checkbox" id="themeSwitch" v-model="isEnabled" />
        <label for="themeSwitch" class="toggle">
            <span class="toggle__handler">
                <span class="crater crater--1"></span>
                <span class="crater crater--2"></span>
                <span class="crater crater--3"></span>
            </span>
            <span class="star star--1"></span>
            <span class="star star--2"></span>
            <span class="star star--3"></span>
            <span class="star star--4"></span>
            <span class="star star--5"></span>
            <span class="star star--6"></span>
        </label>
    </div>
</template>

<script>
    export default {
        props: ['initialState'],
        data () {
            return {
                isEnabled: this.initialState || false
            }
        },
        watch: {
            isEnabled: function (newValue) {
                this.$emit('switched', newValue)
            }
        }
    }
</script>

<style lang="scss" scoped>

    .toggleWrapper input {
        display: none;
    }

    .toggle {
        cursor: pointer;
        display: inline-block;
        position: relative;
        width: 45px;
        height: 25px;
        background-color: #83D8FF;
        border-radius: 84px;
        transition: background-color 200ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
    }
    .toggle:before {
        position: absolute;
        left: -25px;
        top: 7px;
        font-size: 9px;
    }
    .toggle:after {
        position: absolute;
        right: -24px;
        top: 7px;
        font-size: 9px;
        color: #749ED7;
    }

    .toggle__handler {
        display: inline-block;
        position: relative;
        z-index: 1;
        top: 1px;
        left: 1px;
        width: 22px;
        height: 22px;
        background-color: #FFCF96;
        border-radius: 50px;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
        transition: all 400ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
        transform: rotate(-45deg);
    }
    .toggle__handler .crater {
        position: absolute;
        background-color: #E8CDA5;
        opacity: 0;
        transition: opacity 200ms ease-in-out;
        border-radius: 100%;
    }
    .toggle__handler .crater--1 {
        top: 9px;
        left: 5px;
        width: 2px;
        height: 2px;
    }
    .toggle__handler .crater--2 {
        top: 14px;
        left: 11px;
        width: 3px;
        height: 3px;
    }
    .toggle__handler .crater--3 {
        top: 5px;
        left: 13px;
        width: 4px;
        height: 4px;
    }

    .star {
        position: absolute;
        background-color: #f8faff;
        transition: all 300ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
        border-radius: 50%;
    }

    .star--1 {
        top: 5px;
        left: 17px;
        z-index: 0;
        width: 15px;
        height: 1px;
    }

    .star--2 {
        top: 9px;
        left: 14px;
        z-index: 1;
        width: 15px;
        height: 1px;
    }

    .star--3 {
        top: 14px;
        left: 20px;
        z-index: 0;
        width: 15px;
        height: 1px;
    }

    .star--4,
    .star--5,
    .star--6 {
        opacity: 0;
        transition: all 300ms 0 cubic-bezier(0.445, 0.05, 0.55, 0.95);
    }

    .star--4 {
        top: 8px;
        left: 6px;
        z-index: 0;
        width: 1px;
        height: 1px;
        transform: translate3d(1px, 0, 0);
    }

    .star--5 {
        top: 16px;
        left: 8px;
        z-index: 0;
        width: 1px;
        height: 1px;
        transform: translate3d(1px, 0, 0);
    }

    .star--6 {
        top: 18px;
        left: 14px;
        z-index: 0;
        width: 1px;
        height: &px;
        transform: translate3d(1px, 0, 0);
    }

    input:checked + .toggle {
        background-color: #6b65a7;
    }
    input:checked + .toggle:before {
        color: #749ED7;
    }
    input:checked + .toggle:after {
        color: #f8faff;
    }
    input:checked + .toggle .toggle__handler {
        background-color: #FFE5B5;
        transform: translate3d(20px, 0, 0) rotate(0);
    }
    input:checked + .toggle .toggle__handler .crater {
        opacity: 1;
    }
    input:checked + .toggle .star--1 {
        width: 1px;
        height: 1px;
    }
    input:checked + .toggle .star--2 {
        width: 2px;
        height: 2px;
        transform: translate3d(-2px, 0, 0);
    }
    input:checked + .toggle .star--3 {
        width: 1px;
        height: 1px;
        transform: translate3d(-3px, 0, 0);
    }
    input:checked + .toggle .star--4,
    input:checked + .toggle .star--5,
    input:checked + .toggle .star--6 {
        opacity: 1;
        transform: translate3d(0, 0, 0);
    }
    input:checked + .toggle .star--4 {
        transition: all 300ms 200ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
    }
    input:checked + .toggle .star--5 {
        transition: all 300ms 300ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
    }
    input:checked + .toggle .star--6 {
        transition: all 300ms 400ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
    }
</style>