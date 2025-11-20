<script setup>
const now = new Date();
const currentYear = now.getFullYear();
</script>

<template>
    <div class="lg:pt-[6em] pt-[3em] ">
        <div
            class="bg-[#C7C4B7] flex flex-col lg:flex-row border-t-1 border-[#960001] lg:px-[12em] px-[1em] lg:py-[6em] py-[3em]">
            <div class="lg:w-[30%] flex lg:flex-col justify-center items-center ">
                <img src="~/assets/images/icon.avif" alt="Falcom United" class="h-[10em]">
                <div class="my-[1em]">
                    <p class="lg:text-center lg:text-[1.5em] text-[1.25em]">©{{ currentYear }} <NuxtLink to="/"
                            class="hover:text-[#C3292C] text-[#960001] font-semibold">Falcom United</NuxtLink>.</p>
                    <p class="lg:text-center text-black/60 lg:text-[1.5em] text-[1.25em]">All Rights Reserved</p>
                </div>
            </div>
            <div class="lg:px-[5em] lg:w-[70%]">
                <div
                    class="lg:border-l-1 border-[#960001] flex flex-col justify-between gap-[2em] py-[1em] h-[100%] lg:px-[2em]">
                    <p class="text-center text-black/80 lg:text-[1.5em] text-[1.25em]">We deliver certified, skilled
                        construction
                        personnel to support global projects, backed by 20+ years of
                        experience with major clients like <strong>Saudi Aramco</strong>,
                        <strong>Sabic</strong>, <strong>Maaden</strong>, <strong>SCECO</strong>, and
                        <strong>Marafiq</strong>.
                    </p>
                    <div class="flex justify-evenly lg:text-[1.35em] text-[1.2em]">
                        <NuxtLink to="#about" :class="['hover:text-[#C3292C]']">About</NuxtLink>
                        <NuxtLink to="#services" :class="['hover:text-[#C3292C]']">Services</NuxtLink>
                        <NuxtLink to="#values" :class="['hover:text-[#C3292C]']">Values</NuxtLink>
                        <NuxtLink to="#contact" :class="['hover:text-[#C3292C]']">Contact</NuxtLink>
                    </div>
                    <div>
                        <p class="text-center lg:text-[1.25em] text-black/60">Designed & Developed By
                            <a href="" class="font-semibold text-[#003049] hover:text-[#415a77]">AdsAura Productions</a>
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>