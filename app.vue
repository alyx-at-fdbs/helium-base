<template>
    <HeSection is="header" height="4rem" background="var(--color-background)" sticky shadow="m" divider-position="absolute-outer">
        <HeLimiter>
            <HeFlex height="4rem" horizontal gap="1rem">
                <HeLogo href="/" src="https://img.logoipsum.com/297.svg" alt="Logo Ipsum"/>
                <HeSpacer />
                <HeMenu :menu="menu" mobile-submenu-show-toggle />
            </HeFlex>
        </HeLimiter>
        <template #below>
            <HeShapeDivider shape="waves" height=".75rem" background="var(--color-background)"/>
        </template>
    </HeSection>

    <HeSection background="var(--bg-blue-50)">
        <HeLimiter>
            <HeFlex horizontal padding="4rem 0" gap="2rem">
                <HeFlex flex="1">
                    <h1 style="margin: 0; color: var(--bg-blue-500);">Iodine + Helium</h1>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ipsum praesentium dignissimos dolorem
                        perferendis sequi aut exercitationem deserunt eos ratione asperiores excepturi quaerat non cum alias ab, qui
                        numquam eius!
                    </p>
                </HeFlex>
                <HeFlex flex="1">
                    <IodCarousel dots arrows infinite :interval="5000" overlay style="height: 400px; border-radius: 16px;">
                        <template #slide-1>
                            <Visualizer />
                        </template>
                        <template #slide-2>
                            <Visualizer />
                        </template>
                    </IodCarousel>
                </HeFlex>
            </HeFlex>
        </HeLimiter>
        <template #below>
            <HeShapeDivider shape="arrow" height="2rem" background="var(--bg-blue-50)"/>
        </template>
    </HeSection>

    <HeSection>
        <HeLimiter>
            <HeFlex padding="4rem 0" gap="2rem">
                <h2>Button Preview</h2>
                <PreviewButton />
            </HeFlex>
        </HeLimiter>
    </HeSection>

    <footer>
        <HeSection is="div" background="var(--bg-blue-50)">
            <template #above>
                <HeShapeDivider shape="waves" height=".75rem" background="var(--bg-blue-50)" flip-y />
            </template>
            <HeLimiter>
                <HeFlex horizontal padding="4rem 0" gap="2rem" y-align="flex-start">
                    <HeFlex gap="1rem" flex="1">
                        <h3 style="margin: 0; color: var(--bg-blue-500);">Contact</h3>
                        <HeDivider />
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                            <NuxtLink to="/">Menu Item 3</NuxtLink>
                            <NuxtLink to="/">Menu Item 4</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex gap="1rem" flex="1">
                        <h3 style="margin: 0; color: var(--bg-blue-500);">About us</h3>
                        <HeDivider />
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex gap="1rem" flex="1">
                        <h3 style="margin: 0; color: var(--bg-blue-500);">Resources</h3>
                        <HeDivider />
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                            <NuxtLink to="/">Menu Item 3</NuxtLink>
                            <NuxtLink to="/">Menu Item 4</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex gap="1rem" flex="1">
                        <h3 style="margin: 0; color: var(--bg-blue-500);">Legal Information</h3>
                        <HeDivider />
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                            <NuxtLink to="/">Menu Item 3</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                </HeFlex>
            </HeLimiter>
        </HeSection>
        <HeSection is="div" background="var(--bg-blue-500)" style="--color-text: white; color: #ffffffcc;">
            <HeLimiter>
                <HeFlex horizontal height="4rem">
                    <small>© {{ new Date().getFullYear() }} Logo Ipsum</small>
                    <HeSpacer />
                    <IodIconButton icon-font="var(--font-brand)" is="a" href="#" target="_blank" variant="text" shape="pill" icon="&#62002;" aria-label="WhatsApp" />
                    <IodIconButton icon-font="var(--font-brand)" is="a" href="#" target="_blank" variant="text" shape="pill" icon="&#61805;" aria-label="Instagram" />
                    <IodIconButton icon-font="var(--font-brand)" is="a" href="#" target="_blank" variant="text" shape="pill" icon="&#61594;" aria-label="Facebook" />
                </HeFlex>
            </HeLimiter>
        </HeSection>
    </footer>
</template>

<script lang="ts" setup>
    const menu = ref([
        { id: 'home', label: 'Home', href: '/' },
        { id: 'get-started', label: 'Get Started', href: '/' },
        { id: 'components', label: 'Components', href: '/', children: [
            { id: 'button', label: 'Button', href: '/' },
            { id: 'input', label: 'Input', href: '/' },
            { id: 'select', label: 'Select', href: '/' },
            { id: 'checkbox', label: 'Checkbox', href: '/' },
            { id: 'radio', label: 'Radio', href: '/' },
            { id: 'switch', label: 'Switch', href: '/' },
        ] },
        { id: 'demo', label: 'Demo', href: '/' },
    ])
</script>