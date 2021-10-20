<template>
    
    <app-layout>
        <template #header>
            <h1 class="text-center text-2xl font-bold leading-7 text-gray-300 sm:text-3xl sm:truncate py-4 bg-gradient-to-l from-gray-600 to-gray-800">
                Lista de Estudiantes
            </h1>
        </template>

        <div class="py-12">
            <div class=" max-w-7xl mx-auto sm:px-6 lg-px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">

                    <!-- Boton de crear -->

                    <inertia-link
                    :href="route('students.create')"
                    class="flex-shrink-0 bg-green-500 text-white text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-green-500 focus:ring-offset-2 focus:ring-offset-green-200" type="button">
                        Agregar
                    </inertia-link>
                    

                    <table class="rounded-t-lg mt-5 min-w-full mx-auto bg-gray-800 text-gray-100">

                        <thead>
                            <tr class="text-left border-b border-gray-300">
                                <th scope="cool" class="px-6 py-3 text-left text-xs font-medium text-gray-100 uppercase tracking-wider">Nombre</th>
                                <th scope="cool" class="px-6 py-3 text-left text-xs font-medium text-gray-100 uppercase tracking-wider">Correo</th>
                                <th scope="cool" class="px-6 py-3 text-left text-xs font-medium text-gray-100 uppercase tracking-wider">Teléfono</th>
                                <th scope="cool" class="px-6 py-3 text-center text-xs font-medium text-gray-100 uppercase tracking-wider">Opciones</th>
                            </tr>
                        </thead>

                        <tbody class="bg-gray-700 border-gray-600 text-gray-200">
                            <tr v-for="student in students" :key="student.id">

                                <td>
                                    {{student.name}}
                                </td>

                                <td>
                                    {{student.mail}}
                                </td>

                                <td>
                                    {{student.phone}}
                                </td>

                                <inertia-link 
                                :href="route('students.edit', student.id)"
                                class="flex-shrink-0 bg-blue-500 text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-blue-700 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:ring-offset-blue-200">
                                    Editar
                                </inertia-link>

                                <inertia-link 
                                method="delete"
                                :href="route('students.destroy', student.id)"
                                class="flex-shrink-0 bg-red-500 text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-red-700 focus:ring-2 focus:ring-red-500 focus:ring-offset-2 focus:ring-offset-red-200" type="button">
                                    Eliminar
                                </inertia-link>
                            </tr>
                        </tbody>

                    </table>

                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    

    

import AppLayout from "@/Layouts/AppLayout";
export default {
    props:{
        students: Array
    },
    components:{
        AppLayout
    }

};
</script>