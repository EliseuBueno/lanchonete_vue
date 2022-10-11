<template>
    <div>
        <table class="table table-hover table-bordered">
            <thead class="table-dark text-center">
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Cliente</th>
                    <th scope="col">Pão</th>
                    <th scope="col">Carne</th>
                    <th scope="col">Opcionais</th>
                    <th scope="col">Ações</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="burger in burgers" :key="burger.id">
                    <th scope="row">{{burger.id}}</th>
                    <td>{{burger.nome}}</td>
                    <td>{{burger.pao}}</td>
                    <td>{{burger.carne}}</td>
                    <td>
                        <li v-for="(opcional, index) in burger.opcionais" :key="index">{{opcional}}</li>
                    </td>
                    <td>
                        <select class="form-select form-select-sm mb-3" name="status" id="carne" v-model="carne">
                            <option value="">Selecione</option>
                            <option v-for="s in status" value="s.tipo" :key="s.id" :selected="burger.status == s.tipo">
                                {{s.tipo}}
                            </option>
                        </select>
                        <button class="btn btn-danger" value="Cancelar">Cancelar</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>    
</template>

<script>
export default {
    name: 'Dashboard',
    data() {
        return {
            burgers: null,
            burger_id: null,
            status: [],
        }
    },
    methods: {
        async getPedidos() {
            const req = await fetch('http://localhost:3000/burgers')
            const data = await req.json()
            this.burgers = data
             
            this.getStatus()
        },

        async getStatus() {
            const req = await fetch('http://localhost:3000/status')
            const data = await req.json()
            this.status = data

            console.log(data)
        }
    },
    mounted() {
        this.getPedidos()
    }
}
</script>
