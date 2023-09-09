<script>
import axios from 'axios'
export default {
    name: 'AppMain',
    data() {
        return {
            baseUrl: 'http://localhost:8000',
            projects: [],
            loading: true
        }
    },
    created() {
        this.getProjects();
    },
    methods: {
        getProjects() {
            this.loading = true;
            axios.get(`${this.baseUrl}/api/projects`).then((response) => {
                console.log(response);
                if (response.data.success) {
                    this.projects = response.data.result;
                    this.loading = false;

                }
            })
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <h1 class="text-center">Boolpress</h1>
            </div>
            <div class="cointainer">
                <div class="row">
                    <div class="col-12" v-for="project in projects" :key="project.id">
                        {{ project.nome_progetto }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style></style>