<template>
    <footer class="footer-site">
        <div class="container">
            <div class="footer row">
                <div class="col-lg-4 col-md-6 mb-4">
                <br>
                    <div class="rodape card h-100">    
                        <div class="card-body text-center">    
                            <h1 class="card-title">
                                <p class="h1">YES NOW</p>
                            </h1>
                            <p class="h6">Olá Seu shopping é Aqui!</p>
                            <btn-cadastrar/>
                        </div>          
                    </div>
                </div>

                <div class="col-lg-4 col-md-6 mb-4">
                <br>
                    <div class="rodape card h-100">
                        <div class="card-body">
                            <h4 class="card-title">
                                <p class="h5">PÁGINAS:</p>
                            </h4>
                            <p class="card-text">
                                <a href="https://yesnow.ml" class="text-white">Home</a>
                            </p>
                            <p class="card-text">
                                <a href="https://yesnow.ml/Vitrine" class="text-white">Produtos</a>
                            </p>
                            <p class="card-text">
                                <a href="https://yesnow.ml/lojas" class="text-white">Lojas</a>
                            </p>
                            <p class="card-text">
                                <a href="https://yesnow.ml/meus-pedidos.php" class="text-white">Pedidos</a>
                            </p>
                        </div>
                        
                    </div>
                </div>
                <div class="col-lg-4 col-md-6 mb-4">
                <br>
                    <div class="rodape card h-100 ">     
                        <div class="card-body">    
                            <h4 class="card-title">
                                <p class="h5">CONTATO:</p>
                            </h4>
                            <p class="card-text">
                                <i class="icon-mail" aria-hidden="true">adm@bueno.cf</i>
                            </p>
                            <p class="card-text">
                                <i class="icon-whatsapp text-success" aria-hidden="true"></i>
                                (19) 9 9457-7247
                            </p>
                            <p class="card-text">Cidade: Indaiatuba/SP</p>
                            <p class="card-text">CNPJ: 27.982.084/0001-62</p>
                            <a class="btn btn-primary text-center" target="_blank" href="https://web.facebook.com/profile.php?id=100001884876424"> 
                                <i class="icon-facebook" aria-hidden="true"></i>
                                <a class="btn btn-danger text-center" target="_blank" href="https://www.instagram.com/eliseu_sturaro_bueno/"> 
                                    <i class="icon-instagram" aria-hidden="true"></i>
                                </a>
                            </a>
                        </div>
                    </div>
                </div> 
            </div>
            <div class="col-sm-12 col-md-12">
            <br><br>
                <p class="m-0 text-center text-white">Copyright &copy; Eliseu S. Bueno - <a href="https://www.yesnow.ml">www.yesnow.ml  </a></p>
            </div>
        </div>
    </footer>
</template>

<script>
import BtnCadastrar from '../buttons/BtnCadastrar.vue';
export default {
    name: "Footer",
    components: { BtnCadastrar }
}
</script>

<style scoped>
    .footer-site{
        background-image: url('/public/img/pes.jpg');
        background-position: center top;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        color: #ffffff;
        padding-top: 100px;
        padding-bottom: 100px;
    }
    
    .rodape{
        background-color: rgba(0,0,0,0.7);
    }

    .footer{
        background: black;
        opacity: 0.8;    
    }

    .rodape:hover{
        background: black;
        opacity: 0.8;
    }

    .grow:hover{
        -webkit-transform: scale(1.1);
        -ms-transform: scale(1.1);
        transform: scale(1.1);
        opacity: 0.7;
    }
</style>