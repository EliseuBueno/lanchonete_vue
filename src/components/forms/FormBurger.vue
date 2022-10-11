<template>
    <div>
        <h3>Formulário de Cadastro de Burguers</h3>
        <form action="" class="text-left">
            <div class="form-floating mb-3">
                <input type="email" class="form-control" id="floatingInput" placeholder="Digite o nome do cliente">
                <label for="floatingInput">Nome do cliente:</label>
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
export default {
    name: 'FormBurger',
    data() {
        return {
            paes: null,
            carnes: null,
            opcionaisdata: null,
            nome: null,
            pao: null,
            carne: null,
            opcionais: [],
            status: 'Solicitado',
            msg: null,
            user:{},
        }
    },
    created() {
        this.getIngredientes()
    },
    methods: {
        getIngredientes() {
       axios
         .get('http://localhost:3000/ingredientes')
         .then((res) => {
            this.paes = res.data.paes
            this.carnes = res.data.carnes
            this.opcionaisdata = res.data.opcionais
         })
         .catch((error) => {
           console.log(error);
         });
     },
    },
}
</script>