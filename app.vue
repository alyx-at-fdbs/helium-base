<template>
    <HeSection is="header" height="4rem" background="var(--color-background)" sticky shadow="m" divider-position="absolute-outer">
        <HeLimiter>
            <HeFlex height="4rem" horizontal gap="1rem">
                <HeLogo href="/" src="https://img.logoipsum.com/297.svg" alt="Logo Ipsum"/>
                <HeSpacer />
                <HeMenu :menu="menu" mobile-submenu-show-toggle />
                <IodButton is="a" href="/login" size="small" shape="pill" label="Anmelden" color-preset="info"/>
            </HeFlex>
        </HeLimiter>
        <template #below>
            <HeShapeDivider shape="waves" height=".5rem" background="var(--color-background)" flip-x/>
        </template>
    </HeSection>

    <HeSection background="var(--bg-blue-50)">
        <HeLimiter>
            <HeFlex padding="4rem 0">
                <IodCarousel dots arrows infinite :interval="5000" overlay style="height: 500px; border-radius: 4px;">
                    <template #slide-1>
                        <Visualizer />
                    </template>
                    <template #slide-2>
                        <Visualizer />
                    </template>
                </IodCarousel>
        
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ipsum praesentium dignissimos dolorem
                    perferendis sequi aut exercitationem deserunt eos ratione asperiores excepturi quaerat non cum alias ab, qui
                    numquam eius!
                </p>
            </HeFlex>
        </HeLimiter>
        <template #below>
            <HeShapeDivider shape="waves" height="2rem" background="var(--bg-blue-50)" />
        </template>
    </HeSection>

    <HeSection>
        <HeLimiter>
            <HeFlex padding="4rem 0">
                <h2>Section Title</h2>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ipsum praesentium dignissimos dolorem
                    perferendis sequi aut exercitationem deserunt eos ratione asperiores excepturi quaerat non cum alias ab, qui
                    numquam eius!
                </p>
            </HeFlex>
        </HeLimiter>
    </HeSection>

    <footer>
        <HeSection is="div" background="var(--bg-blue-100)" divider-position="absolute-inner">
            <template #above>
                <HeShapeDivider shape="waves" height="1rem" background="var(--color-background)" flip-x />
            </template>
            <HeLimiter>
                <HeFlex horizontal padding="2rem 0 3rem" gap="1rem" y-align="flex-start">
                    <HeFlex :style="{flex: 1}">
                        <h3 style="color: var(--bg-blue-500);">Contact</h3>
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                            <NuxtLink to="/">Menu Item 3</NuxtLink>
                            <NuxtLink to="/">Menu Item 4</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex :style="{flex: 1}">
                        <h3 style="color: var(--bg-blue-500);">About us</h3>
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex :style="{flex: 1}">
                        <h3 style="color: var(--bg-blue-500);">Resources</h3>
                        <HeFlex>
                            <NuxtLink to="/">Menu Item 1</NuxtLink>
                            <NuxtLink to="/">Menu Item 2</NuxtLink>
                            <NuxtLink to="/">Menu Item 3</NuxtLink>
                            <NuxtLink to="/">Menu Item 4</NuxtLink>
                        </HeFlex>
                    </HeFlex>
                    <HeFlex :style="{flex: 1}">
                        <h3 style="color: var(--bg-blue-500);">Legal Information</h3>
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
        { id: 'about', label: 'About', href: '/about' },
        { id: 'contact', label: 'Contact', href: '/contact' },
        { id: 'nachhaltigkeit', label: 'Nachhaltigkeit', href: '/nachhaltigkeit/co2-kuehlung', children: [
            { id: 'co2-kuehlung', label: 'CO\u2082 Kühlung', href: '/nachhaltigkeit/co2-kuehlung', children: [] },
            { id: 'ecobox', label: 'EcoBox', href: '/nachhaltigkeit/ecobox', children: [] },
            { id: 'oekostrom', label: 'Ökostrom', href: '/nachhaltigkeit/oekostrom', children: [] },
        ] },
    ])
</script>