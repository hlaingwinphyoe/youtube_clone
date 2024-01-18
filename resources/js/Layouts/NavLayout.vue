<template>
    <div class="relative">
        <div
            id="TopNav"
            class="w-full h-[60px] fixed bg-black z-20 flex items-center justify-between"
        >
            <div class="flex items-center">
                <button
                    @click="openSideNav = !openSideNav"
                    class="p-2 ml-3 rounded-full hover:bg-gray-800 inline-block cursor-pointer"
                >
                    <MenuIcon fillColor="#ffffff" :size="26" />
                </button>
                <div class="mx-2"></div>
                <div
                    class="flex text-white items-center justify-center mr-10 cursor-pointer"
                >
                    YOUTUBE
                </div>
            </div>

            <div class="w-[600px] md:block hidden">
                <div class="rounded-full flex items-center bg-[#222222]">
                    <input
                        type="text"
                        class="form-control block w-full px-5 py-1.5 text-base font-normal text-gray-200 bg-black placeholder-gray-400 bg-clip-padding border border-solid border-l-gray-700 border-y-gray-700 rounded-l-full transition ease-in-out m-0 border-transparent focus:ring-0"
                        placeholder="Search"
                    />
                    <MagnifyIcon class="mx-6" fillColor="#ffffff" :size="23" />
                </div>
            </div>

            <div>
                <img
                    class="rounded-full mx-8"
                    width="35"
                    src="https://yt3.ggpht.com/yti/AGOGRCr6_C2g0oVtnkv7Ds3uXZjskp2zwQ0kG0HBSA=s88-c-k-c0x00ffffff-no-rj-mo"
                    alt=""
                />
            </div>
        </div>
        <div
            id="SideNav"
            :class="[!openSideNav ? 'w-[80px]' : 'w-[240px]']"
            class="h-full fixed z-0 bg-black"
        >
            <ul
                :class="[!openSideNav ? 'p-2' : 'px-4 pb-2 pt-[7px]']"
                class="mt-[60px] w-full"
            >
                <SideNavItem :openSideNav="openSideNav" iconString="Home" />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Add Video"
                />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Delete Video"
                />
                <div class="border-b border-b-gray-700 my-2.5"></div>
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Subscriptions"
                />
                <SideNavItem :openSideNav="openSideNav" iconString="Library" />
                <SideNavItem :openSideNav="openSideNav" iconString="Liked" />
                <SideNavItem :openSideNav="openSideNav" iconString="History" />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Watch Later"
                />
                <div v-if="openSideNav">
                    <div class="border-b border-b-gray-700 my-2.5"></div>
                    <div class="text-gray-400 text-sm font-extrabold">
                        About Press Copyright
                        <div>Contact us</div>
                        Creator Advertise Developers
                    </div>
                    <div class="border-b border-b-gray-700 my-2.5"></div>
                    <div class="text-gray-400 text-sm font-extrabold">
                        Terms Privacy Policy & Safety
                        <div>How Youtube works?</div>
                        <span>Test new features</span>
                    </div>
                </div>
            </ul>
        </div>
        <div id="SideNavOverlay"></div>
        <div
            class="w-full h-[calc(100vh-60px)] absolute right-0 top-[60px]"
            :class="{
                'w-[calc(100%-80px)]': !openSideNav,
                'w-[calc(100%-240px)]': openSideNav,
            }"
        >
            <slot />
        </div>
    </div>
</template>

<script setup>
import MenuIcon from "vue-material-design-icons/Menu.vue";
import MagnifyIcon from "vue-material-design-icons/Magnify.vue";
import SideNavItem from "@/Components/SideNavItem.vue";
import { ref } from "vue";

const openSideNav = ref(true);
</script>

<style>
body {
    background: black;
}
</style>
