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
        hobbies.value = document.querySelector('#hobbies').value
        linguagens.value = document.querySelector('#linguagens').value
        biografia.value = document.querySelector('#biografia').value
    }
}

function voltar() {
    document.querySelector('.form').style.display = 'flex'
    document.querySelector('.resposta').style.display = 'none'
    document.querySelector('#name').value = ''
    document.querySelector('#email').value = ''
    document.querySelector('#senha').value = ''
    document.querySelector('#confirme').value = ''
    document.querySelector('#nascimento').value = ''
    document.querySelector('#adress').value = ''
    document.querySelector('#cidade').value = ''
    document.querySelector('#estado').value = ''
    document.querySelector('#hobbies').value = ''
    document.querySelector('#linguagens').value = ''
    document.querySelector('#biografia').value = ''
}



</script>

<template>
    <form class="form" @submit.prevent="submit">
        <label for="name">Informe seu nome:</label>
        <input id="name" type="text" required>


        <label for="email">Informe seu e-mail:</label>
        <input id="email" type="email" required>

        <label for="senha">Informe sua senha:</label>
        <input id="senha" type="password" required>

        <label for="confirme">Confirme sua senha:</label>
        <input id="confirme" type="password" required>

        <label for="nascimento">Informe sua data de nascimento:</label>
        <input id="nascimento" type="date" required>

        <label for="adress">Informe seu endereço:</label>
        <input id="adress" type="text" required>

        <label for="cidade">Informe sua cidade:</label>
        <input id="cidade" type="text" required>

        <label for="estado">Informe seu estado:</label>
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

        <label for="hobbies">Informe seu hobbie favorito:</label>
        <input id="hobbies" type="text" required>

        <label for="linguagens">Informe as linguagens de programacão que você domina:</label>
        <input id="linguagens" type="text" required>

        <label for="biografia">Escreva uma sua biografia:</label>
        <textarea name="biografia" id="biografia" cols="50" rows="10" maxlength="1000"></textarea>


        <button type="submit">Enviar </button>
    </form>

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
    border-radius: 5px;
    border: 1px solid #000;
    margin-top: 2px;
    margin-bottom: 10px;
    font-family: "Poppins", sans-serif;
    font-weight: 5 00;
    font-style: normal;
    font-size: 1px;

}

label {
    margin-left: 25%;
    margin-top: 10px;
}

select {
    width: 50%;
    height: 30px;
    margin-left: 25%;
    border-radius: 5px;
    border: 1px solid #000;
}

button[type="submit"] {
    width: 50%;
    height: 30px;
    margin-top: 3%;
    margin-left: 25%;
    border-radius: 5px;
    border: 1px solid #000;
    background-color: #000;
    color: #fff;
}

option,
select {
    background-color: purple;
}

textarea {
    resize: none;
    width: 50%;
    margin-left: 25%
}

.resposta {
    display: none;
}
</style>
