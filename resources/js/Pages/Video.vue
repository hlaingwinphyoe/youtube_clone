<template>
    <Head title="Youtube" />
    <NavLayout>
        <div class="xl:flex">
            <div class="p-3">
                <video src="/videos/test.mp4" controls autoplay></video>
                <div class="text-white text-xl font-extrabold mt-4">
                    A Cool Video
                </div>
                <div class="flex items-center mb-4">
                    <img
                        class="rounded-full m-1.5 mt-2 flex items-baseline w-8 h-8"
                        :src="
                            `https://picsum.photos/id/${(
                                Math.random() * 100
                            ).toFixed(0)}/100` || ''
                        "
                        alt=""
                    />
                    <div class="pl-2 mt-1">
                        <div
                            class="text-white font-extrabold gap-1 flex items-center"
                        >
                            DevOps
                            <CheckCircle fillColor="#ffffff" :size="13" />
                        </div>
                        <div class="text-sm text-gray-400 font-extrabold">
                            1.2k subscribers
                        </div>
                    </div>
                </div>

                <!-- Video Descripton & Comment Section -->
                <div class="bg-[#2e2e2e] rounded-lg w-full p-3 text-white">
                    <div class="text-white font-extrabold text-[15px]">
                        1.2k views &nbsp; 3 days ago
                    </div>
                    <div class="text-sm font-extrabold mb-6">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Dicta, possimus!
                    </div>
                    <div class="text-sm font-extrabold">
                        Lorem ipsum dolor sit amet consectetur, adipisicing
                        elit. Quia vel ducimus porro. Eius, tempore sunt.
                    </div>
                </div>

                <div class="mt-6">
                    <div class="text-white font-extrabold">12 Comments</div>
                    <div class="flex items-center mb-4 mt-2">
                        <img
                            class="rounded-full w-10 h-10"
                            :src="
                                `https://picsum.photos/id/${(
                                    Math.random() * 100
                                ).toFixed(0)}/100` || ''
                            "
                            alt=""
                        />
                        <div class="pl-4 text-sm">
                            <div
                                class="text-white font-extrabold flex items-baseline"
                            >
                                <div>Alex Smith</div>
                                <div class="text-gray-400 pl-3">6 days ago</div>
                            </div>
                            <div class="text-gray-200 text-sm font-semibold">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem provident, quod eum harum natus nisi libero, consectetur officia, ratione delectus odit. Suscipit placeat ut maiores ipsam deserunt commodi necessitatibus temporibus!
                            </div>
                            <div class="mt-3 flex items-center">
                                <ThumbUpOutline fillColor="#ffffff" :size="18" class="pr-2" />
                                <div class="text-gray-400 text-sm font-extrabold pr-5">
                                    {{ (Math.random() * 100).toFixed(0) }}
                                </div>
                                <ThumbDownOutline fillColor="#ffffff" :size="18" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </NavLayout>
</template>
<script setup>
import { Head, Link } from "@inertiajs/vue3";
import NavLayout from "@/Layouts/NavLayout.vue";
import CheckCircle from "vue-material-design-icons/CheckCircle.vue";
import ThumbUpOutline from "vue-material-design-icons/ThumbUpOutline.vue";
import ThumbDownOutline from "vue-material-design-icons/ThumbDownOutline.vue";
</script>
