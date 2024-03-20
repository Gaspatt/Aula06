<script setup>
import { ref } from 'vue'

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

if (senha.value !== confirme.value) {
    alert('As senhas não são iguais')
}

function submit () {
    document.querySelector('.form').style.display = 'none'
    document.querySelector('.resposta').style.display = 'block'
    name.value = document.querySelector('#name').value
    email.value = document.querySelector('#email').value
    senha.value = document.querySelector('#senha').value
    confirme.value = document.querySelector('#confirme').value
    nascimento.value = document.querySelector('#nascimento').value
    adress.value = document.querySelector('#adress').value
    cidade.value = document.querySelector('#cidade').value
    estado.value = document.querySelector('#estado').value
    hobbies.value = document.querySelector('#hobbies&shaw').value
    linguagens.value = document.querySelector('#linguagens').value
    biografia.value = document.querySelector('#biografia').value
}

</script>

<template>
    <div class="form">
        <label for="name">Informe seu nome:</label>
        <input id="name" type="text">


        <label for="email">Informe seu e-mail:</label>
        <input id="email" type="email">

        <label for="senha">Informe sua senha:</label>
        <input id="senha" type="password">

        <label for="confirme">Confirme sua senha:</label>
        <input id="confirme" type="password">

        <label for="nascimento">Informe sua data de nascimento:</label>
        <input id="nascimento" type="date">

        <label for="adress">Informe seu endereço:</label>
        <input id="adress" type="text">

        <label for="cidade">Informe sua cidade:</label>
        <input id="cidade" type="text">

        <label for="estado">Informe seu estado:</label>
        <select id="estado" name="estado">
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

        <label for="hobbies&shaw">Informe seu hobbie favorito</label>
        <input id="hobbies&shaw" type="text">

        <label for="linguagens">Informe as linguagens de programacão que você domina:</label>
        <input id="linguagens" type="text">

        <label for="biografia">Escreva uma sua biografia</label>
        <textarea name="" id="biografia" cols="50" rows="10" maxlength="1000" ></textarea>


        <input id="submit" type="submit" value="Enviar" @click="submit">
    </div>

    <div class="resposta">
        <h1>Resposta</h1>
        <p>Nome: {{ name }}</p>
        <p>Email: {{ email }}</p>
        <p>Senha: {{ senha }}</p>
        <p>Confirme: {{ confirme }}</p>
        <p>Nascimento: {{ nascimento }}</p>
        <p>Adress: {{ adress }}</p>
        <p>Cidade: {{ cidade }}</p>
        <p>Estado: {{ estado }}</p>
        <p>Hobbies: {{ hobbies }}</p>
        <p>Linguagens: {{ linguagens }}</p>
        <p>Biografia: {{ biografia }}</p>
    </div>

</template>

<style scoped>

    .form {
        display: flex;
        flex-direction: column; 
        margin-top: 50px;
    }

    input {
        width: 300px;
        height: 30px;
        border-radius: 5px;
        border: 1px solid #000;
        margin-top: 2px;
        margin-bottom: 10px;

    }

    select {
        width: 300px;
        height: 30px;
        border-radius: 5px;
        border: 1px solid #000;
    }

    input[type="submit"] {
        width: 300px;
        height: 30px;
        border-radius: 5px;
        border: 1px solid #000;
        background-color: #000;
        color: #fff;
    }

    input[type="submit"]:hover {
        background-color: #888888;
        color: #000;
    }

    textarea {
        resize: none;
    }

    .resposta {
        display: none;
    }
    
    
</style>
