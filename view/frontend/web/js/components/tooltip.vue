<template>
    <span v-if="showTooltip" v-tooltip="{content, offset}"><slot /></span>
</template>

<script>
define([
    'Vue',
    'VTooltip'
], function (Vue, VTooltip) {

    Vue.component('tooltip', {
        template: template,
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
