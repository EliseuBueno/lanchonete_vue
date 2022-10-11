<template>
    <div>
        <Message :msg="msg" v-show="msg" />
        <h3>Formulário de Cadastro de Burguers</h3>
        <form id="form-burger" @submit="createBurger" class="text-left">
            <div class="form-floating mb-3">
                <input type="text" class="form-control" id="nome" name="nome" v-model="nome" placeholder="Digite o nome do cliente">
                <label for="nome">Nome do cliente:</label>
            </div>
            <div>
                <label for="pao">Escolha o pão</label>
                <select class="form-select form-select-lg mb-3" name="pao" id="pao" v-model="pao">
                    <option selected>Selecione o pão</option>
                    <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{pao.tipo}}</option>
                </select>
            </div>
            <div>
                <label for="carne">Escolha a carne</label>
                <select class="form-select form-select-lg mb-3" name="carne" id="carne" v-model="carne">
                    <option selected>Selecione a carne</option>
                    <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{carne.tipo}}</option>
                </select>
            </div>
            <div class="form-check form-switch text-start">
                <label class="form-check-label" for="opcionais">Selecione os opcionais:</label>
                <div v-for="opcional in opcionaisdata" :key="opcional.id">
                    <input 
                        class="form-check-input" 
                        type="checkbox" 
                        role="switch" 
                        id="opcionais" 
                        name="opcionais" 
                        v-model="opcionais" 
                        :value="opcional.tipo"
                    >
                    <span>{{opcional.tipo}}</span>
                </div>
            </div>
            <br>
            <div class="text-center">
                <button type="submit" class="btn btn-primary" value="Criar meu Burguer">Criar</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from "axios";
import Message from "../Message.vue";
export default {
    name: "FormBurger",
    data() {
        return {
            paes: null,
            carnes: null,
            opcionaisdata: null,
            nome: null,
            pao: null,
            carne: null,
            opcionais: [],
            msg: null,
            user: {},
        };
    },
    created() {
        this.getIngredientes();
    },
    methods: {
        getIngredientes() {
            axios
                .get("http://localhost:3000/ingredientes")
                .then((res) => {
                this.paes = res.data.paes;
                this.carnes = res.data.carnes;
                this.opcionaisdata = res.data.opcionais;
            })
                .catch((error) => {
                console.log(error);
            });
        },
        async createBurger(e) {
            e.preventDefault();
            const data = {
                nome: this.nome,
                carne: this.carne,
                pao: this.pao,
                opcionais: Array.from(this.opcionais),
                status: "Solicitado",
            };
            const dataJson = JSON.stringify(data);
            const req = await fetch("http://localhost:3000/burgers", {
                method: "POST",
                headers: { "Content-type": "application/json" },
                body: dataJson
            });
            const res = await req.json();

            this.msg = `Pedido Nº ${res.id} realizado com Sucesso!`

            setTimeout(()=> this.msg = "", 3000)

            this.nome = "";
            this.carne = "";
            this.pao = "";
            this.opcionais = "";

        }
    },
    components: { Message }
}
</script>