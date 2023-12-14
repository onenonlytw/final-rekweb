<script setup>
import {Link} from '@inertiajs/vue3';

    defineProps({
        users: Object,
    })
</script>

<template>
    <div class="max-w-7xl m-auto mt-10">
        <div class="overflow-x-auto">
            <Link href="/user/create" class="btn btn-primary mb-5">Create User</Link>
            <table class="table">
                <!-- head -->
                <thead>
                <tr>
                    <th></th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Action</th>
                </tr>
                </thead>
                <tbody>
                <!-- row 1 -->
                <tr v-for="user in users">
                    <th>{{ user.id }}</th>
                    <td>{{ user.name }}</td>
                    <td>{{ user.email }}</td>
                    <td>
                        <Link :href="route('user.edit', user.id)" class="btn btn-warning">Edit</Link>
                        &nbsp;
                        <Link :href="route('user.destroy', user.id)" method="delete" class="btn btn-error">Delete</Link>
                    </td>
                </tr>
                
                </tbody>
            </table>
        </div>
    </div>
</template>