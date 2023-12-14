<script setup>
import { useForm } from '@inertiajs/vue3';


    const form = useForm({
        name: '',
        email: '',
        password: ''
    })
</script>

<template>
    <div class="max-w-7xl m-auto mt-10">
        <form @submit.prevent="form.post('/user')">
            <label class="form-control w-full max-w-xs">
            <div class="label">
                <span class="label-text">Name</span>
            </div>
            <input type="text" v-model="form.name" name="name" placeholder="test" class="input input-bordered w-full max-w-xs" />
            </label>

            <label class="form-control w-full max-w-xs">
                <div class="label">
                    <span class="label-text">Email</span>
                </div>
                <input type="email" v-model="form.email" name="email" placeholder="test@test.com" class="input input-bordered w-full max-w-xs" />
            </label>

            <label class="form-control w-full max-w-xs">
                <div class="label">
                    <span class="label-text">Password</span>
                </div>
                <input type="password" v-model="form.password" name="password" placeholder="12345678" class="input input-bordered w-full max-w-xs" />
            </label>

            <input type="submit" value="Save" class="btn btn-success text-white mt-5">
        </form>
    </div>
</template>