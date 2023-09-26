<script setup>
    
    import { Head, Link } from '@inertiajs/vue3';
    import AppLayout from '@/Layouts/AppLayout.vue';
    import EditIcon from './EditIcon.vue';
    import DeleteIcon from './DeleteIcon.vue';

    defineProps({
        posts: Array,
    });

</script>

<template>
    <AppLayout title="Dashboard">
        <div class="pt-12">
            <h2 class="text-center font-semibold text-3xl text-gray-800 leading-tight">
                 My To Do List
            </h2>
        </div>

        <div class="py-2">
            <div class="min-h-screen flex flex-col items-center pt-6 sm:pt-0">
                <div class="py-12">
                    <Link href="/posts/create" class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">Add To Do</Link>
                </div>
                <div class="bg-gray-50">
                    <table class="table-auto">
                        <tbody class="">
                            <tr v-for="post in posts" :key="post.id">
                                <td class="border px-4 py-2">
                                    <input type="checkbox">
                                </td>
                                <td class="border px-36 py-2">{{ post.title }}</td>
                                <td class="border px-2 py-2">
                                    <div class="flex">
                                        <Link :href="'posts/'+post.id+'/edit'"><EditIcon class="block h-8 w-auto px-2"/></Link>
                                        <Link :href="'posts/'+post.id+'/delete'"><DeleteIcon class="block h-8 w-auto px-2" /></Link>
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                  </table>
                </div>
            </div>
        </div>
    </AppLayout>
</template>