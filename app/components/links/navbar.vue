<script setup>
const activeSection = ref('home')
const isMenuOpen = ref(false)

const handleScroll = () => {
    const sections = ['home', 'about', 'services', 'values', 'contact']

    for (const section of sections) {
        const element = document.getElementById(section)
        if (element) {
            const rect = element.getBoundingClientRect()
            if (rect.top <= 100 && rect.bottom >= 100) {
                activeSection.value = section
                break
            }
        }
    }
}

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
}

const navigateAndClose = (section) => {
    isMenuOpen.value = false
    document.getElementById(section)?.scrollIntoView({ behavior: 'smooth' })
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
    handleScroll()
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
    <div class="relative">
        <div
            class="bg-black/20 backdrop-blur-lg border-1 border-[#C7C4B7] rounded-full lg:py-[1em] py-[0.5em] lg:px-[2em] px-[1em] flex justify-between gap-[0.5em] text-white">
            <NuxtLink to="#home" class="flex items-center lg:gap-[0.5em]">
                <img src="~/assets/images/icon.avif" alt="Falcom United" class="h-[4em]">
                <p class="font-[800] text-[1.25em] leading-none">Falcom United</p>
            </NuxtLink>

            <div class="hidden lg:flex gap-[2.5em] items-center">
                <NuxtLink to="#about"
                    :class="['hover:text-[#C3292C]', activeSection === 'about' && 'text-[#960001] font-bold']">
                    About
                </NuxtLink>
                <NuxtLink to="#services"
                    :class="['hover:text-[#C3292C]', activeSection === 'services' && 'text-[#960001] font-bold']">
                    Services
                </NuxtLink>
                <NuxtLink to="#values"
                    :class="['hover:text-[#C3292C]', activeSection === 'values' && 'text-[#960001] font-bold']">
                    Values
                </NuxtLink>
                <NuxtLink to="#contact"
                    :class="['hover:text-[#C3292C]', activeSection === 'contact' && 'text-[#960001] font-bold']">
                    Contact
                </NuxtLink>
            </div>

            <button @click="toggleMenu" class="md:hidden flex items-center" aria-label="Toggle menu"
                :aria-expanded="isMenuOpen">
                <p class="capitalize font-semibold">{{ activeSection }}</p>
                <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960" width="24px"
                    fill="#ffffff" :class="['transition-transform duration-300', isMenuOpen && 'rotate-180']">
                    <path d="M480-344 240-584l56-56 184 184 184-184 56 56-240 240Z" />
                </svg>
            </button>
        </div>

        <Transition enter-active-class="transition-all duration-300 ease-out"
            enter-from-class="opacity-0 -translate-y-2" enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition-all duration-200 ease-in" leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 -translate-y-2">
            <div v-if="isMenuOpen" class="absolute top-full left-0 right-0 mt-2 md:hidden">
                <div class="bg-black/30 backdrop-blur-lg border border-[#C7C4B7] rounded-2xl overflow-hidden shadow-xl">
                    <NuxtLink to="#home" @click="navigateAndClose('home')" :class="[
                        'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                        activeSection === 'home' && 'bg-[#960001]/20 text-[#C3292C] font-bold'
                    ]">
                        Home
                    </NuxtLink>
                    <NuxtLink to="#about" @click="navigateAndClose('about')" :class="[
                        'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                        activeSection === 'about' && 'bg-[#960001]/20 text-[#C3292C] font-bold'
                    ]">
                        About
                    </NuxtLink>
                    <NuxtLink to="#services" @click="navigateAndClose('services')" :class="[
                        'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                        activeSection === 'services' && 'bg-[#960001]/20 text-[#C3292C] font-bold'
                    ]">
                        Services
                    </NuxtLink>
                    <NuxtLink to="#values" @click="navigateAndClose('values')" :class="[
                        'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                        activeSection === 'values' && 'bg-[#960001]/20 text-[#C3292C] font-bold'
                    ]">
                        Values
                    </NuxtLink>
                    <NuxtLink to="#contact" @click="navigateAndClose('contact')" :class="[
                        'block px-6 py-4 text-white hover:bg-white/10 transition-colors',
                        activeSection === 'contact' && 'bg-[#960001]/20 text-[#C3292C] font-bold'
                    ]">
                        Contact
                    </NuxtLink>
                </div>
            </div>
        </Transition>
    </div>
</template>