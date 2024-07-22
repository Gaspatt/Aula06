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

        linguagens.value = document.querySelectorAll('input[name="linguagens"]:checked')[0].value

        biografia.value = document.querySelector('#biografia').value
    }
}

function reset() {
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

        <div class="h1">
            <h1>Formulário de Cadastro</h1>
        </div>
        <div class="divmain divv">
            <label for="name">Informe seu nome: <span class="ast">*</span></label>
            <input id="name" type="text" required min="3" max="100">
        </div>

        <div class="divmain">
            <label for="email">Informe seu e-mail: <span class="ast">*</span></label>
            <input id="email" type="email" required>
        </div>

        <div class="divmain">
            <label for="senha">Informe sua senha: <span class="ast">*</span></label>
            <input id="senha" type="password" required>
        </div>

        <div class="divmain">
            <label for="confirme">Confirme sua senha: <span class="ast">*</span></label>
            <input id="confirme" type="password" required>
        </div>

        <div class="divmain">
            <label for="nascimento">Informe sua data de nascimento: <span class="ast">*</span></label>
            <input id="nascimento" type="date" min="1900-01-31" max="2024-12-31" required>
        </div>

        <div class="divmain">
            <label for="adress">Informe seu endereço: <span class="ast">*</span></label>
            <input id="adress" type="text" required>
        </div>

        <div class="divmain">
            <label for="cidade">Informe sua cidade: <span class="ast">*</span></label>
            <input id="cidade" type="text" required>
        </div>

        <div class="divmain">
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
        </div>

        <div class="divmain">
            <label for="hobbies">Informe seu hobbie favorito: <span class="ast">*</span>
            </label>
        </div>

        <div class="divmain">
            <div class="checkbox">
                <input type="checkbox" id="filmes" name="filmes" value="Filmes">
                <label for="filmes">Filmes</label>

                <input type="checkbox" id="livros" name="livros" value="Livros">
                <label for="livros">Livros</label>

                <input type="checkbox" id="jogos" name="jogos" value="Jogos">
                <label for="jogos">Jogos</label>

                <input type="checkbox" id="comidas" name="comidas" value="Comidas">
                <label for="comidas">Comidas</label>

                <input type="checkbox" id="lugares" name="lugares" value="Lugares">
                <label for="lugares">Lugares</label>


            </div>
        </div>

        <div class="divmain">
            <label for="linguagens">Informe as linguagens de programacão que você domina: <span
                    class="ast">*</span></label>
        </div>
        <div class="divmain">
            <div class="radio">
                <input type="radio" id="js" name="linguagens" value="Java Script">
                <label for="js">JavaScript</label>

                <input type="radio" id="py" name="linguagens" value="Python">
                <label for="py">Python</label>

                <input type="radio" id="java" name="linguagens" value="Java">
                <label for="java">Java</label>

                <input type="radio" id="c" name="linguagens" value="C">
                <label for="c">C</label>
            </div>
        </div>

        <div class="divmain">
            <label for="biografia">Escreva uma sua biografia: <span class="ast">*</span></label>
            <textarea name="biografia" id="biografia" cols="50" rows="10" maxlength="1000"
                v-model="biografia"></textarea>
        </div>

<div class="botoes">
    <button type="submit">Enviar</button>
    <button type="reset" v-on="reset">Resetar</button>
</div>
 
    </form>

    <div class="resposta">
        <div class="h1">
            <h1>Informações do usuário</h1>
        </div>
        <div class="pdiv">
            
            <div class="p">
                <p>Nome: <span> {{ name }}</span></p>
            </div>
            <div class="p">
                <p>Email: <span> {{ email }}</span></p>
            </div>
            <div class="p">
                <p>Senha: <span>{{ senha }}</span></p>
            </div>
            <div class="p">
                <p>Confirmação de senha: <span> {{ confirme }} </span></p>
            </div>
            <div class="p">
                <p>Nascimento: <span> {{ nascimento }} </span></p>
            </div>
            <div class="p">
                <p>Endereço: <span> {{ adress }}</span></p>
            </div>
            <div class="p">
                <p>Cidade: <span> {{ cidade }} </span></p>
            </div>
            <div class="p">
                <p>Estado: <span> {{ estado }} </span></p>
            </div>
            <div class="p">
                <p>Hobbies: <span> {{ hobbies }} </span></p>
            </div>
            <div class="p">
                <p>Linguagens: <span> {{ linguagens }} </span></p>
            </div>
            <div class="p" id="rbio">
                <p>Biografia: <span> {{ biografia }} </span></p>
            </div>
        </div>
        <input id="voltar" type="submit" value="Voltar" @click="voltar">
        
    </div>



</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

body {
    background-color: white;
}

span {
    font-weight: bold;
}

.checkbox {
    color: rgb(255, 255, 255);
    width: 50%;
    margin-left: 15%;
    display: flex;
    align-items: end;
}

.checkbox label {
    color: rgb(255, 255, 255);
    margin-left: 10px;

}

.radio {
    color: rgb(255, 255, 255);
    width: 50%;
    margin-left: 12%;
    display: flex;
    align-items: end;
}

.radio label {
    color: rgb(255, 255, 255);
    margin-left: 10px;
}

.h1 {
    width: 100%;
    text-align: center;
    font-size: 1.5rem;
    color: white;
    font-weight: bolder;
    margin-top: 1vh;
    margin-bottom: 1vh;
}

h1 {
    font-weight: bold;
}

.form {
    display: flex;
    flex-direction: column;
    box-shadow: 2px 5px 25px 25px rgba(0, 0, 0, 0.281);
    margin-top: 50px;
    width: 200%;
    background-color: #38005e83;
    border-radius: 25px;
    margin-bottom: 10%;

}

.checkbox input {
    margin-left: 8%;
}

.divv {
    border-radius: 25px;
}

.poppins-light {
    font-family: "Poppins", sans-serif;
    font-weight: 300;
    font-style: normal;
}

input {
    width: 70%;
    padding: 5px;
    height: 30px;
    margin-left: 15%;
    margin-bottom: 4vh;
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
    margin-left: 15%;
    margin-top: 10px;
    color: #fff;
    margin-bottom: 1vh;
    font-size: 18px;
}



.ast {
    color: red;
}

select {
    width: 70%;
    height: 30px;
    margin-left: 15%;
    border-radius: 5px;
    border: 1px solid #000;
}

.checkbox {
    
}

.botoes {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-bottom: 3%;
    margin-top: 3%;
}
button[type="submit"] {
    width: 30%;
    height: 5vh;
    font-size: 20px;
    border-radius: 20px;
    border: 1px solid #000;
    background-color: #440e75;
    color: #fff;
    cursor: pointer;
    margin-right: 5%
}

button[type="reset"] {
    width: 30%;
    height: 5vh;
    font-size: 20px;
    border-radius: 20px;
    border: 1px solid #000;
    background-color: #5c5275;
    color: #fff;
    cursor: pointer;
}

select {
    border-radius: 15px;
    padding: 5px;
}

option {
    cursor: pointer;
}

textarea {
    resize: none;
    border-radius: 15px;
    width: 70%;
    margin-left: 15%
}

.resposta {
    display: flex;
    flex-direction: column;
    margin-top: 50px;
    width: 200%;
    background-color: #38005e83;
    box-shadow: 2px 5px 25px 25px rgba(0, 0, 0, 0.281);
    border-radius: 25px;
    margin-bottom: 10%;
    display: none;
    color: white;
    text-align: center;
    justify-content: center;
    margin-left: 0%;
}

#rbio {
    height: 10vh;
    overflow-y: scroll;
    margin-bottom: 20px;
    margin-top: 20px;
    padding: 10px;
    border-radius: 10px;
    width: 70%;
    margin-left: 15%;
    background-color: white;
    color: black;
    font-size: 15px;
    text-indent: 10px;
    text-align: justify;
    
}

.resposta input {
    background-color: #440e75;
    color: white;
    height: 5vh;
    margin-left: 0
}

.resposta .pdiv {
    width: 100%;
}

.resposta .p {
    background-color: white;
    color: black;
    width: 70%;
    margin-bottom: 20px;
    height: 5vh;
    margin-left: 15%;
    border-radius: 10px;
    text-align: justify;
    text-indent: 15px;
}

.resposta h1 {
    font-weight: bold;
    margin-bottom: 2.5%;
    margin-top: 2%;
}
</style>
