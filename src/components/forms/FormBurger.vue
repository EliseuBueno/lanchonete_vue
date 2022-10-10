<template>
    <div>
        <h3>Formulário de Cadastro de Burguers</h3>
        <form action="">
            <div class="form-floating mb-3">
                <input type="email" class="form-control" id="floatingInput" placeholder="Digite o nome do cliente">
                <label for="floatingInput">Nome do cliente:</label>
            </div>
            <div>
                <label for="pao">Escolha o pão</label>
                <select class="form-select form-select-lg mb-3" name="pao" id="pao" v-model="pao">
                    <option selected>Selecione o pão</option>
                    <option value="integral">Integral</option>
                </select>
            </div>
            <div>
                <label for="carne">Escolha a carne</label>
                <select class="form-select form-select-lg mb-3" name="carne" id="carne" v-model="carne">
                    <option selected>Selecione a carne</option>
                    <option value="contra-file">Contra-Filé</option>
                </select>
            </div>
            <div class="form-check form-switch text-start">
                <label class="form-check-label" for="opcionais">Selecione os opcionais:</label>
                <div>
                    <input 
                        class="form-check-input" 
                        type="checkbox" 
                        role="switch" 
                        id="opcionais" 
                        name="opcionais" 
                        v-model="opcionais" 
                        value="opcionais"
                    >
                    <span>Salame</span>
                </div>
            </div>
            <div>
                <button type="submit" class="btn btn-primary" value="Criar meu Burguer">Criar</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'FormBurger',
}
</script>