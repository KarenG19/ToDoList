<script setup>
    
    import { useForm } from '@inertiajs/vue3';
    import AppLayout from '@/Layouts/AppLayout.vue';

    defineProps({
        posts: Array,
    });

    const form = useForm({
        title: '',
    });

    function submit(){
        form.post('/posts');
    }

</script>

<template>
    <AppLayout title="Dashboard">
        <div class="pt-12">
            <h2 class="text-center font-semibold text-3xl text-gray-800 leading-tight">
                Add To Do
            </h2>
        </div>

        <div class="py-6">
            <div class="min-h-screen flex flex-col items-center pt-6 sm:pt-0">
                <div class="bg-gray-200 shadow-md rounded-lg">
                    <div class="px-6 py-2">
                        <form class="w-full" @submit.prevent="submit()">
                            <div class="py-12 flex flex-col items-center">
                                <div class="">
                                    <input v-model="form.title" class="rounded-md shadow-sm border-slate-300" autofocus>
                                </div>
                                <div class="pt-6">
                                    <Button class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-8 rounded">Add</Button>
                                </div>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>