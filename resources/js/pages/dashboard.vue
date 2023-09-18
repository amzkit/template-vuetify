<template>
    <div class="w-100">
        <v-row justify="center">
            <v-col>
                <v-card>
                    <v-card-title>Dashboard</v-card-title>
                    <v-card-text>Current User : {{ user }}</v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </div>
</template>

<script>

export default {
    components: {  },
    data: () => ({
        user: null,
    }),

    computed: {

    },

    watch: {
      
    },

    created () {
       this.initialize()
    },

    methods: {
        async initialize () {
            await axios
                .get('/api/v1/user')
                .then(response => {
                    this.user = response.data
                })
                .catch(error => {
                    this.errors = error.response.data.errors
                })
        },
        async getData(){
            
        },
    

    },
};
</script>
