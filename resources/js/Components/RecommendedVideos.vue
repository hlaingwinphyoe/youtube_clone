<template>
    <div @mouseover="show = true" @mouseleave="show = false">
        <img
            width="340"
            class="aspect-video rounded-lg cursor-pointer"
            :src="vid.thumbnail || ''"
            :class="show ? 'delay-350 hidden' : ''"
            alt=""
        />
        <div
            class="w-full h-full aspect-video cursor-pointer"
            :class="show ? '' : 'delay-350 hidden'"
        >
            <video
                width="340"
                ref="video"
                :src="vid.video || ''"
                type="video/mp4"
            ></video>
        </div>
    </div>

    <div class="w-[500px]">
        <div class="px-1.5 pl-3 text-white mt-1">
            <div
                class="text-[16px] pb-1.5 font-extrabold w-full cursor-pointer"
            >
                {{ vid.title }}
            </div>
            <div
                class="text-[12px] text-gray-300 font-extrabold flex gap-1 items-center cursor-pointer"
            >
                {{ vid.user }}
                <CheckCircle fillColor="#ffffff" :size="13" />
            </div>
            <div class="text-xs text-gray-300 cursor-pointer">
                {{ vid.views }}
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, toRefs, watch } from "vue";
import CheckCircle from "vue-material-design-icons/CheckCircle.vue";

const props = defineProps({ vid: Object });
const { vid } = toRefs(props);

let show = ref(false);
let video = ref(null);

watch(
    () => show.value,
    (show) => {
        if (show) {
            video.value.play();
            return "";
        }
        video.value.pause();
        video.value.currentTime = 0;
    }
);
</script>
