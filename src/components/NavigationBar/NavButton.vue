<script lang="ts">
export default {
    name: 'NavButton',
    props: {
				text: {
						type: String,
						default: 'Button',
				},
				color: {
						type: String,
						default: '#000000',
				},
				backgroundColor: {
						type: String,
						default: '#ffffff',
				},
				borderColor: {
						type: String,
						default: '#cccccc30',
				},
        hoverColor: {
            type: String,
            default: '#ffffff',
        },
        hoverBackgroundColor: {
            type: String,
            default: '#000000',
        },
				hoverBorderColor: {
						type: String,
						default: '#000000',
				},
    },
    data() {
        return {
            currentColor: this.color,
            currentBackgroundColor: this.backgroundColor,
						currentBorderColor: this.borderColor,
        };
    },
    methods: {
        mouseOver() {
            this.currentColor = this.hoverColor;
            this.currentBackgroundColor = this.hoverBackgroundColor;
						this.currentBorderColor = this.hoverBorderColor;
        },
        mouseOut() {
            this.currentColor = this.color;
            this.currentBackgroundColor = this.backgroundColor;
						this.currentBorderColor = this.borderColor;
        },
    },
};
</script>

<template>
<button
    :style="{ color: currentColor, backgroundColor: currentBackgroundColor, borderColor: currentBorderColor }"
    @mouseover="mouseOver"
    @mouseout="mouseOut"
>
    {{ text }}
</button>
</template>
<style scoped>
	button {
		border: 1px solid #cccccc30;
		border-radius: 15px;
		padding: 1rem 1.5rem;
		font-size: 0.8rem;
		font-weight: bold;
		cursor: pointer;
		transition: all 0.3s ease-in-out;
	}

</style>