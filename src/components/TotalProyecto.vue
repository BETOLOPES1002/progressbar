<template>
    <hr>
    <h3>
        <div class="row">
            <div class="col-6 my-3">
                Total Proyectos: {{ numeroProyectos }}
            </div>
        </div>
    </h3>
    <div class="table-responsive">
    
        <table class="table table-dark table-hover">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Proyecto</th>
                    <th>Tipo</th>
                    <th>Urgente</th>
                </tr>
            </thead>

            <tbody>
                <tr v-for="(proyecto, index) in proyectos" :key="index">
                    <td>{{ index+1 }}</td>
                    <td> {{ proyecto.proyecto }} </td>
                    <td> {{ proyecto.tipo }} </td>
                    <td @click="cambiarEstado(proyecto, 'urgente')" :class="proyecto.urgente ? 'bg-success' : 'bg-danger'"> {{ proyecto.urgente ? "Si" : "No" }} </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>


<script>
    export default{
        props: ['numeroProyectos','proyectos', 'cambiarEstado'],
        
    };
</script>