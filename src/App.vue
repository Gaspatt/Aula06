<script setup>
import { ref, onBeforeUpdate } from 'vue'

const name = ref('')
const email = ref('')
const senha = ref('')
const confirme = ref('')
const nascimento = ref('')
const adress = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref('')
const linguagens = ref('')
const biografia = ref('')





function submit() {
    if (document.querySelector('#senha').value !== document.querySelector('#confirme').value) {
        alert('As senhas não são iguais')
    }
    else {
        document.querySelector('.form').style.display = 'none'
        document.querySelector('.resposta').style.display = 'block'
        name.value = document.querySelector('#name').value
        email.value = document.querySelector('#email').value
        senha.value = document.querySelector('#senha').value
        confirme.value = document.querySelector('#confirme').value
        nascimento.value = document.querySelector('#nascimento').value
        adress.value = document.querySelector('#adress').value
        cidade.value = document.querySelector('#cidade').value
        estado.value = document.querySelectorAll('#estado option')[document.querySelector('#estado').selectedIndex].text
        hobbies.value = ''
        if (document.querySelector('#filmes').checked) {
            hobbies.value += 'Filmes, '
        }
        if (document.querySelector('#livros').checked) {
            hobbies.value += 'Livros, '
        }
        if (document.querySelector('#jogos').checked) {
            hobbies.value += 'Jogos, '
        }
        if (document.querySelector('#comidas').checked) {
            hobbies.value += 'Comidas, '
        }
        if (document.querySelector('#lugares').checked) {
            hobbies.value += 'Lugares '
        }


        hobbies.value = document.querySelector('#hobbies').value
        linguagens.value = document.querySelector('#linguagens').value
        biografia.value = document.querySelector('#biografia').value
    }
}

function voltar() {
    document.querySelector('.form').style.display = 'flex'
    document.querySelector('.resposta').style.display = 'none'
    document.querySelector('#name').value
    document.querySelector('#email').value
    document.querySelector('#senha').value
    document.querySelector('#confirme').value
    document.querySelector('#nascimento').value
    document.querySelector('#adress').value
    document.querySelector('#cidade').value
    document.querySelector('#estado').value
    document.querySelector('#hobbies').value
    document.querySelector('#linguagens').value
    document.querySelector('#biografia').value
}



</script>

<template>
    <form class="form" @submit.prevent="submit">
        <label for="name">Informe seu nome: <span class="ast">*</span></label>
        <input id="name" type="text" required min="3" max="100">


        <label for="email">Informe seu e-mail: <span class="ast">*</span></label>
        <input id="email" type="email" required>

        <label for="senha">Informe sua senha: <span class="ast">*</span></label>
        <input id="senha" type="password" required>

        <label for="confirme">Confirme sua senha: <span class="ast">*</span></label>
        <input id="confirme" type="password" required>

        <label for="nascimento">Informe sua data de nascimento: <span class="ast">*</span></label>
        <input id="nascimento" type="date" required>

        <label for="adress">Informe seu endereço: <span class="ast">*</span></label>
        <input id="adress" type="text" required>

        <label for="cidade">Informe sua cidade: <span class="ast">*</span></label>
        <input id="cidade" type="text" required>

        <label for="estado">Informe seu estado: <span class="ast">*</span></label>
        <select id="estado" name="estado" required>
            <option value="AC">Acre</option>
            <option value="AL">Alagoas</option>
            <option value="AP">Amapá</option>
            <option value="AM">Amazonas</option>
            <option value="BA">Bahia</option>
            <option value="CE">Ceará</option>
            <option value="DF">Distrito Federal</option>
            <option value="ES">Espírito Santo</option>
            <option value="GO">Goiás</option>
            <option value="MA">Maranhão</option>
            <option value="MT">Mato Grosso</option>
            <option value="MS">Mato Grosso do Sul</option>
            <option value="MG">Minas Gerais</option>
            <option value="PA">Pará</option>
            <option value="PB">Paraíba</option>
            <option value="PR">Paraná</option>
            <option value="PE">Pernambuco</option>
            <option value="PI">Piauí</option>
            <option value="RJ">Rio de Janeiro</option>
            <option value="RN">Rio Grande do Norte</option>
            <option value="RS">Rio Grande do Sul</option>
            <option value="RO">Rondônia</option>
            <option value="RR">Roraima</option>
            <option value="SC">Santa Catarina</option>
            <option value="SP">São Paulo</option>
            <option value="SE">Sergipe</option>
            <option value="TO">Tocantins</option>
        </select>

        <label for="hobbies">Informe seu hobbie favorito: <span class="ast">*</span>
        </label>

        <div class="checkbox">
            <input id="filmes" type="checkbox" value="Filmes">
            Filmes
            <input id="livros" type="checkbox" value="Livros">
            Livros
            <input id="jogos" type="checkbox" value="Jogos">
            Jogos
            <input id="comidas" type="checkbox" value="Comidas">
            Comidas
            <input id="lugares" type="checkbox" value="Lugares">
            Lugares
        </div>

        <label for="linguagens">Informe as linguagens de programacão que você domina: <span class="ast">*</span></label>
        <input id="linguagens" type="text" v-model="linguagens" required>

        <label for="biografia">Escreva uma sua biografia: <span class="ast">*</span></label>
        <textarea name="biografia" id="biografia" cols="50" rows="10" maxlength="1000" v-model="biografia"></textarea>


        <button type="submit">Enviar </button>
    </form>

    <div class="resposta">
        <h1>Informações do usuário</h1>
        <div class="pdiv">
            <div class="p">
                <p>Nome: {{ name }}</p>
            </div>
            <div class="p">
                <p>Email: {{ email }}</p>
            </div>
            <div class="p">
                <p>Senha: {{ senha }}</p>
            </div>
            <div class="p">
                <p>Confirme: {{ confirme }}</p>
            </div>
            <div class="p">
                <p>Nascimento: {{ nascimento }}</p>
            </div>
            <div class="p">
                <p>Adress: {{ adress }}</p>
            </div>
            <div class="p">
                <p>Cidade: {{ cidade }}</p>
            </div>
            <div class="p">
                <p>Estado: {{ estado }}</p>
            </div>
            <div class="p">
                <p>Hobbies: {{ hobbies }}</p>
            </div>
            <div class="p">
                <p>Linguagens: {{ linguagens }}</p>
            </div>
            <div class="p" id="rbio">
                <p>Biografia: {{ biografia }}</p>
            </div>
        </div>
        <input id="voltar" type="submit" value="Voltar" @click="voltar">
    </div>



</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.form {
    display: flex;
    flex-direction: column;
    margin-top: 50px;
    width: 200%;
    background-color: #161616;
    border-radius: 25px;
    margin-bottom: 10%;

}

.poppins-light {
    font-family: "Poppins", sans-serif;
    font-weight: 300;
    font-style: normal;
}

input {
    width: 50%;
    padding: 5px;
    height: 30px;
    margin-left: 25%;
    border-radius: 15px;
    border: 1px solid #000;
    margin-top: 2px;
    margin-bottom: 10px;
    font-family: "Poppins", sans-serif;
    font-weight: 5 00;
    font-style: normal;
    font-size: 15px;

}

label {
    margin-left: 25%;
    margin-top: 10px;
    color: #fff
}

.ast {
    color: red;
}

select {
    width: 50%;
    height: 30px;
    margin-left: 25%;
    border-radius: 5px;
    border: 1px solid #000;
}

button[type="submit"] {
    width: 30%;
    height: 30px;
    margin-top: 3%;
    margin-left: 35%;
    margin-bottom: 3%;
    border-radius: 20px;
    border: 1px solid #000;
    background-color: #ff0062;
    color: #fff;
}

select {
    border-radius: 15px;
    padding: 5px;
}

textarea {
    resize: none;
    border-radius: 15px;
    width: 50%;
    margin-left: 25%
}

.resposta {
    display: flex;
    flex-direction: column;
    margin-top: 50px;
    width: 200%;
    background-color: #161616;

    border-radius: 25px;
    margin-bottom: 10%;
    display: none;
    color: white;
    text-align: center;
    justify-content: center;
    margin-left: 0%;
}

.resposta input {
    background-color: #ff0062;
    color: white;
    margin-left: 0
}

.resposta .pdiv {
    width: 100%
}

.resposta .p {
    background-color: white;
    color: black;
    width: 80%;
    margin-bottom: 20px;
    margin-left: 10%;
    border-radius: 10px;
}

.resposta h1 {
    font-weight: bold;
    margin-bottom: 5%
}
</style>
