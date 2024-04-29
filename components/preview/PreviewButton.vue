<template>
    <div class="layout">
        <div class="preview small-scrollbar">
            <b></b>
            <span class="label">size xl</span>
            <span class="label">size l</span>
            <span class="label">size m</span>
            <span class="label">size s</span>
            
            <template v-for="variant in ['filled', 'contained', 'text']">
                <span class="label">{{ variant }}</span>
                <template v-for="size in ['xl', 'l', 'm', 's']">
                    <IodButton
                        v-if="type === 'text'"
                        :icon-left="iconLeft"
                        :icon-right="iconRight"
                        :disabled="disabled"
                        :loading="loading"
                        :border="border"
                        :corner="corner"
                        :shadow="shadow"
                        :color-preset="colorPreset"
                        :variant="variant"
                        :size="size"
                        label="Button"
                    />

                    <IodIconButton
                        v-if="type === 'icon'"
                        :disabled="disabled"
                        :loading="loading"
                        :border="border"
                        :corner="corner"
                        :shadow="shadow"
                        :color-preset="colorPreset"
                        :variant="variant"
                        :size="size"
                        icon="category"
                    />
                </template>
            </template>
        </div>
        <div class="settings small-scrollbar">
            <div class="setting-group">
                <span class="label">Button Type</span>
                <HeFlex horizontal gap="1rem">
                    <IodButton style="flex: 1" :variant="type === 'text' ? 'filled' : 'contained'" @click="type = 'text'" label="Text"/>
                    <IodButton style="flex: 1" :variant="type === 'icon' ? 'filled' : 'contained'" @click="type = 'icon'" label="Icon"/>
                </HeFlex>
            </div>
            <div class="setting-group">
                <span class="label">Color Preset</span>
                <IodSelect class="same-height-input" v-model="colorPreset" :options="[
                    { text: 'Default', value: ''},
                    { text: 'Primary', value: 'primary' },
                    { text: 'Secondary', value: 'secondary' },
                    { text: 'Tertiary', value: 'tertiary' },
                    { text: 'Error', value: 'error' },
                    { text: 'Warning', value: 'warning' },
                    { text: 'Success', value: 'success' },
                    { text: 'Info', value: 'info' },
                ]"/>
            </div>
            <div class="setting-group">
                <span class="label">Corner</span>
                <IodSelect class="same-height-input" v-model="corner" :options="[
                    { text: 'Default – M', value: ''},
                    { text: 'None', value: 'none' },
                    { text: 'Small – S', value: 's' },
                    { text: 'Medium – M', value: 'm' },
                    { text: 'Large – L', value: 'l' },
                    { text: 'Extra Large – XL', value: 'xl' },
                    { text: 'Pill', value: 'pill' },
                ]"/>
            </div>
            <div class="setting-group">
                <span class="label">Shadow</span>
                <IodSelect class="same-height-input" v-model="shadow" :options="[
                    { text: 'Default', value: ''},
                    { text: 'Small – S', value: 's' },
                    { text: 'Medium – M', value: 'm' },
                    { text: 'Large – L', value: 'l' },
                ]"/>
            </div>
            <div class="setting-group">
                <span class="label">Border</span>
                <IodToggle class="same-height-input" label="Border" v-model="border" />
            </div>
            <div class="setting-group">
                <span class="label">States</span>
                <IodToggle class="same-height-input" label="Disabled" v-model="disabled" />
                <IodToggle class="same-height-input" label="Loading" v-model="loading" />
            </div>
            <div class="setting-group" v-show="type === 'text'">
                <span class="label">Icons</span>
                <IodInput class="same-height-input" v-model="iconLeft" placeholder="Left icon" clearable />
                <IodInput class="same-height-input" v-model="iconRight" placeholder="Right icon" clearable />
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
    const type = ref('text')
    const colorPreset = ref('')
    const corner = ref('')
    const border = ref(false)
    const disabled = ref(false)
    const loading = ref(false)
    const iconLeft = ref('')
    const iconRight = ref('')
    const shadow = ref('')
</script>

<style lang="sass" scoped>
    .layout
        display: grid
        grid-template-columns: 1fr 400px
        grid-template-rows: 500px
        grid-template-areas: "preview settings"
        border: 1px solid var(--bg-slate-300)
        border-radius: var(--radius-m)
        // outline: 1px solid var(--bg-slate-400)
        overflow: hidden
        // box-shadow: var(--shadow-s)

        .label
            font-weight: 500
            font-family: var(--font-mono)
            font-size: .8rem
            color: var(--bg-slate-400)
            user-select: none

        .same-height-input
            height: 2.75rem !important

            &.iod-toggle
                background: var(--color-background-soft)

            
        .preview
            grid-area: preview
            display: grid
            grid-template-columns: 100px 1fr 1fr 1fr 1fr
            grid-template-rows: 3rem 1fr 1fr 1fr
            gap: 1rem
            padding: 2rem 1rem
            align-items: center
            justify-items: center
            overflow: auto

            > b
                font-family: var(--font-mono)
                font-weight: 600

        .settings
            grid-area: settings
            border-left: 1px solid var(--bg-slate-200)
            display: flex
            flex-direction: column
            overflow: auto

            .setting-group
                display: flex
                flex-direction: column
                gap: .5rem
                padding: 1rem
                border-bottom: 1px solid var(--bg-slate-200)

                &:last-child
                    border-bottom: none
</style>