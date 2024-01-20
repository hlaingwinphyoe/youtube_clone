<template>
    <Head title="Youtube" />
    <NavLayout>
        <div class="max-w-2xl mx-auto p-4">
            <div class="text-white font-extrabold mb-4 text-xl">Add Video</div>
            <form class="space-y-6">
                <div>
                    <InputLabel for="title" value="Title" />

                    <TextInput
                        id="title"
                        type="text"
                        class="mt-1 block w-full"
                        required
                        autofocus
                        autocomplete="title"
                    />

                    <InputError class="mt-2" message="Error" />
                </div>
                <div>
                    <InputLabel for="thumbnail" value="Thumbnail" />

                    <input
                        id="thumbnail"
                        type="file"
                        class="block w-full px-3 py-1.5 border text-white border-solid border-gray-600 rounded-md transition ease-in-out m-0 focus:text-gray-700 focus:border-violet-600 focus:outline-none"
                    />

                    <InputError class="mt-2" message="Error" />
                </div>

                <div>
                    <InputLabel for="video" value="Video/MP4" />

                    <input
                        id="video"
                        type="file"
                        class="block w-full px-3 py-1.5 border text-white border-solid border-gray-600 rounded-md transition ease-in-out m-0 focus:text-gray-700 focus:border-violet-600 focus:outline-none"
                    />

                    <InputError class="mt-2" message="Error" />
                </div>
                <div class="text-right">
                    <PrimaryButton>Submit</PrimaryButton>
                </div>
            </form>
        </div>
    </NavLayout>
</template>

<script setup>
import NavLayout from "@/Layouts/NavLayout.vue";
import { Head } from "@inertiajs/vue3";
import InputError from "@/Components/InputError.vue";
import InputLabel from "@/Components/InputLabel.vue";
import TextInput from "@/Components/TextInput.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
</script>
