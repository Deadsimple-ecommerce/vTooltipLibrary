<template>
    <span v-if="showTooltip" v-tooltip="{content, offset, trigger}"><slot /></span>
</template>

<script>
define([
    'Vue',
    'VTooltip'
], function (Vue, VTooltip) {

    Vue.component('tooltip', {
        template: template,
        data() {
            return {
                trigger: window.innerWidth > 768 ? 'hover' : 'click'
            }
        },
        directives: {
            tooltip: VTooltip.VTooltip,
        },
        props: {
            content: {
                type: String,
                default: ''
            },
            offset: {
                type: Number,
                default: 0
            }
        },
        computed: {
            showTooltip() {
                return this.content !== ''
            }
        }
    });

});
</script>
