<template>
    <Head title="Youtube" />
    <NavLayout>
        <div
            class="grid 2xl:grid-cols-5 xl:grid-cols-4 lg:grid-cols-3 sm:grid-cols-1"
        >
            <!-- Video List -->
            <VideoCard
                title="Cool City View"
                user="CodeX"
                views="23k views - 3 days ago"
                image="https://picsum.photos/id/230/10"
                videoUrl="/videos/test.mp4"
                thumbnail="/videos/test.png"
            />
        </div>
    </NavLayout>
</template>

<script setup>
import { Head, Link } from "@inertiajs/vue3";
import NavLayout from "@/Layouts/NavLayout.vue";
import VideoCard from "@/Components/VideoCard.vue";
</script>
