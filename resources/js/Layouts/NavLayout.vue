<template>
    <div class="relative">
        <div
            id="TopNav"
            class="w-full h-[60px] fixed bg-black z-20 flex items-center justify-between"
        >
            <div class="flex items-center">
                <button
                    @click="isNavOverlay()"
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
        <div v-if="width > 639">
            <div
                v-if="$page.url === '/'"
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
                    <SideNavItem
                        :openSideNav="openSideNav"
                        iconString="Library"
                    />
                    <SideNavItem
                        :openSideNav="openSideNav"
                        iconString="Liked"
                    />
                    <SideNavItem
                        :openSideNav="openSideNav"
                        iconString="History"
                    />
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
        </div>
        <div
            @click="openSideNavOverlay = false"
            class="bg-black bg-opacity-70 fixed z-50 w-full h-screen"
            :class="
                openSideNavOverlay
                    ? 'animate__animated animate__fadeIn animate__faster'
                    : 'hidden z[-1]'
            "
        ></div>
        <div>
            <div
                id="SideNavOverlay"
                ref="sideNavOverlay"
                :class="[
                    openSideNavOverlay
                        ? 'animate__animated animate__slideInLeft animate__faster'
                        : 'animate__animated animate__slideOutLeft animate__faster',
                ]"
                class="h-full fixed z-50 bg-black mt-[9px] w-[240px]"
            >
                <div class="flex items-center">
                    <button
                        @click="isNavOverlay()"
                        class="p-2 ml-3 rounded-full hover:bg-gray-800 cursor-pointer"
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
                <ul class="w-full px-5 py-2 p-2 mt-2">
                    <SideNavItem :openSideNav="true" iconString="Home" />
                    <SideNavItem
                        :openSideNav="true"
                        iconString="Add Video"
                    />
                    <SideNavItem
                        :openSideNav="true"
                        iconString="Delete Video"
                    />
                    <div class="border-b border-b-gray-700 my-2.5"></div>
                    <SideNavItem
                        :openSideNav="true"
                        iconString="Subscriptions"
                    />
                    <SideNavItem
                        :openSideNav="true"
                        iconString="Library"
                    />
                    <SideNavItem
                        :openSideNav="true"
                        iconString="Liked"
                    />
                    <SideNavItem
                        :openSideNav="true"
                        iconString="History"
                    />
                    <SideNavItem
                        :openSideNav="true"
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
        </div>
        <div
            class="w-full h-[calc(100vh-60px)] absolute right-0 top-[60px]"
            :class="{
                'w-[calc(100%-80px)]': !openSideNav,
                'w-[calc(100%-240px)]': openSideNav,
                'w-[100vw] xl:w-[calc(100%-80px)]': $page.url !== '/',
                'w-[100vw]' : width < 639
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
import { onMounted, ref } from "vue";
import { usePage } from "@inertiajs/vue3";

let openSideNav = ref(true);
let openSideNavOverlay = ref(false);
let sideNavOverlay = ref(null);
let width = ref(document.documentElement.clientWidth);

onMounted(() => {
    resize();
    sideNavOverlay.value.classList.value =
        sideNavOverlay.value.classList.value += " hidden";
    window.addEventListener("resize", () => {
        width.value = document.documentElement.clientWidth;
        resize();
    });
});

const resize = () => {
    if (width.value <= 1280 && openSideNav.value) {
        openSideNav.value = false;
    }
    if (width.value > 1279 && !openSideNav.value) {
        openSideNav.value = true;
    }
};

const isNavOverlay = () => {
    if (usePage().url === "/") openSideNav.value = !openSideNav.value;
    if (usePage().url === "/add-video")
        openSideNavOverlay.value = !openSideNavOverlay.value;
    if (usePage().url === "/delete-video")
        openSideNavOverlay.value = !openSideNavOverlay.value;
    if (width.value < 640) openSideNavOverlay.value = !openSideNavOverlay.value;
    if (usePage().url !== "/" && width.value < 640)
        openSideNavOverlay.value = !openSideNavOverlay.value;
    if (usePage().props.video)
        openSideNavOverlay.value = !openSideNavOverlay.value;
        if (usePage().url === '/videos/1')
        openSideNavOverlay.value = !openSideNavOverlay.value;
};
</script>

<style>
body {
    background: black;
}
</style>
