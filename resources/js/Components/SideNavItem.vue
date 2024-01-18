<template>
    <li
        :class="[!openSideNav ? 'p-2' : 'flex items-center px-3 py-2']"
        class="text-white text-sm font-semibold text-center hover:bg-[#222222] rounded-lg cursor-pointer"
    >
        <div
            :class="[
                !openSideNav ? 'w-full flex items-center justify-center' : '',
            ]"
        >
            <component :is="icon" />
        </div>
        <div :class="[!openSideNav ? '' : 'mt-1 ml-2']" class="font-medium">
            <span v-if="!openSideNav" class="text-[8px]">{{ iconString }}</span>
            <span v-else>{{ iconString }}</span>
        </div>
    </li>
</template>

<script setup>
import Home from "vue-material-design-icons/Home.vue";
import FolderPlayOutline from "vue-material-design-icons/FolderPlayOutline.vue";
import ImageMultiple from "vue-material-design-icons/ImageMultiple.vue";
import ThumbUpOutline from "vue-material-design-icons/ThumbUpOutline.vue";
import History from "vue-material-design-icons/History.vue";
import ClockOutline from "vue-material-design-icons/ClockOutline.vue";
import VideoPlusOutlineIcon from "vue-material-design-icons/VideoPlusOutline.vue";
import DeleteIcon from "vue-material-design-icons/Delete.vue";
import { toRefs } from "vue";

const props = defineProps({
    openSideNav: Boolean,
    iconString: String,
});

const { openSideNav, iconString } = toRefs(props);
let icon = null;
if (iconString.value === "Home") icon = Home;
if (iconString.value === "Subscriptions") icon = FolderPlayOutline;
if (iconString.value === "Library") icon = ImageMultiple;
if (iconString.value === "Liked") icon = ThumbUpOutline;
if (iconString.value === "History") icon = History;
if (iconString.value === "Watch Later") icon = ClockOutline;
if (iconString.value === "Add Video") icon = VideoPlusOutlineIcon;
if (iconString.value === "Delete Video") icon = DeleteIcon;
</script>
