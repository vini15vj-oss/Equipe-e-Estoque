# Equipe-e-Estoque
um projeto destinado a ajudar equipes a gerência um estabelecimento alimentício

<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portal Restaurante</title>

<style>

/* RESET */
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

/* CONTAINER */
.container{
    max-width:1200px;
    margin:auto;
}

body{
    background: linear-gradient(135deg, #1993b2, #084c01);
    min-height:100vh;
      padding:20px;
    display:flex;
    color:#111;
}

/* MENU */
.menu{
    width:250px;
    background:#084c01;
    color:white;
    min-height:100vh;
    padding:20px;
}

.menu h2{
    margin-bottom:20px;
    text-align:center;
}

.menu button{
    width:100%;
    padding:12px;
    margin-bottom:10px;
    border:none;
    background:#149b02;
    color:white;
    cursor:pointer;
    border-radius:5px;
    transition:0.3s;
    font-weight:bold;
}

.menu button:hover{
    background:#b7d304;
    color:#000;
}

/* CONTEÚDO */
.conteudo{
    flex:1;
    padding:20px;
    overflow:auto;
}

.tela{
    display:none;
}

.ativa{
    display:block;
}

/* CARDS */
.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:20px;
    margin-top:20px;
}

.card{
    background:white;
    padding:12px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
    text-align:center;
    cursor:pointer;
    transition:0.3s;
}

.card:hover{
    transform:scale(1.05);
    background:#13b8ff;
    color:white;
}

/* FORMULÁRIOS */
input,
select,
textarea{
    width:100%;
    padding:10px;
    margin-top:10px;
    border:1px solid #ccc;
    border-radius:5px;
}

button{
    border:none;
}

/* BOTÕES */
.cadastrar{
    width:100%;
    padding:12px;
    margin-top:15px;
    background:#24cb02;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
    font-size:16px;
    font-weight:bold;
    transition:0.3s;
}

.cadastrar:hover{
    background:#1e9e02;
}

.entrada{
    background:#0ba923;
    color:white;
    padding:10px;
    border-radius:5px;
    cursor:pointer;
}

.saida{
    background:#f44336;
    color:white;
    padding:10px;
    border-radius:5px;
    cursor:pointer;
}

.delete{
    background:red;
    color:white;
    padding:8px;
    border-radius:5px;
    cursor:pointer;
}

/* TABELAS */
table{
    width:100%;
    border-collapse:collapse;
    margin-top:20px;
    background:white;
}

table th,table td{
    border:1px solid #ccc;
    padding:10px;
    text-align:center;
}

table th{
    background:#4493fb;
    color:white;
}

/* RELÓGIO */
#relogio{
    font-size:20px;
    margin:15px 0;
    font-weight:bold;
}

</style>
</head>

<head>
    <style>
body{
    min-height:100vh;
    padding:20px;
    color:white;
}

.container{
    max-width:1200px;
    margin:auto;
}

/* CARDS */
.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:20px;
    margin-bottom:30px;
}

.card{
    background:white;
    color:#111;
    padding:20px;
    border-radius:15px;
    box-shadow:0 5px 15px rgba(0,0,0,0.3);
    transition:0.3s;
}

.card:hover{
    transform:translateY(-5px);
}

.card h2{
    font-size:18px;
    margin-bottom:10px;
}

.card p{
    font-size:25px;
    font-weight:bold;
}

/* FORM */
.formulario{
    background:white;
    color:#111;
    padding:20px;
    border-radius:15px;
    margin-bottom:30px;
    box-shadow:0 5px 15px rgba(0,0,0,0.3);
}

.form-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:15px;
}

input,
select{
    width:100%;
    padding:12px;
    border:1px solid #ccc;
    border-radius:8px;
    font-size:15px;
}

button{
    border:none;
    padding:12px;
    border-radius:8px;
    cursor:pointer;
    font-weight:bold;
    transition:0.3s;
}

.btn-add{
    background:#28a745;
    color:white;
}

.btn-add:hover{
    background:#218838;
}

.btn-delete{
    background:#dc3545;
    color:white;
}

.btn-delete:hover{
    background:#c82333;
}

.btn-edit{
    background:#007bff;
    color:white;
}

.btn-edit:hover{
    background:#0069d9;
}

/* TABELA */
table{
    width:100%;
    border-collapse:collapse;
    background:white;
    color:#111;
    border-radius:15px;
    overflow:hidden;
}

table th{
    background:#007bff;
    color:white;
    padding:15px;
}

table td{
    padding:12px;
    border-bottom:1px solid #ddd;
    text-align:center;
}

.baixo{
    background:#ffb3b3;
    color:#b30000;
    font-weight:bold;
}

.medio{
    background:#fff3cd;
    color:#856404;
    font-weight:bold;
}

.alto{
    background:#c3f7d0;
    color:#155724;
    font-weight:bold;
}

@media(max-width:768px){

    table{
        font-size:12px;
    }

    h1{
        font-size:19px;
    }
}
    </style>
</head>
<body>

<!-- MENU -->
<div class="menu">

    <h2>🍽 Restaurante</h2>

    <button onclick="mostrarTela('dashboard')">Dashboard</button>
    <button onclick="mostrarTela('estoque')">Estoque</button>
    <button onclick="mostrarTela('funcionarios')">Funcionários</button>
    <button onclick="mostrarTela('controle')">Controle de Ponto</button>
    <button onclick="mostrarTela('rh')">RH</button>
    <button onclick="mostrarTela('mesas')">Mesas</button>
    <button onclick="mostrarTela('pedidos')">Pedidos</button>

</div>

<!-- CONTEÚDO -->
<div class="conteudo">

    <!-- DASHBOARD -->
    <div id="dashboard" class="tela ativa">

        <h1> 🏪Portal do Restaurante</h1>

        <div class="cards">

            <div class="card" onclick="mostrarTela('controle')">
                <h2>⏰ Controle de Ponto</h2>
                <p>Registro de entrada e saída</p>
            </div>

            <div class="card" onclick="mostrarTela('funcionarios')">
                <h2>👨‍🍳 Funcionários</h2>
                <p>Cadastro completo</p>
            </div>

            <div class="card" onclick="mostrarTela('estoque')">
                <h2>📦 Estoque</h2>
                <p>Estoque de total de produtos </p>
            </div>

            <div class="card" onclick="mostrarTela('mesas')">
                <h2>🪑 Mesas</h2>
                <p>Status das mesas</p>
            </div>

            <div class="card" onclick="mostrarTela('pedidos')">
                <h2>🧾 Pedidos</h2>
                <p>Controle de pedidos</p>
            </div>

        </div>

    </div>

    <!-- ESTOQUE -->
    <div id="estoque" class="tela">

        <h1>📦 Estoque</h1>
        <p>Área de estoque em desenvolvimento.</p>

        <div class="cards">

        <div class="card">
            <h2>Total de Produtos</h2>
            <p id="totalProdutos">0</p>
        </div>

        <div class="card">
            <h2>Itens em Baixa</h2>
            <p id="baixoEstoque">0</p>
        </div>

        <div class="card">
            <h2>Valor Total</h2>
            <p id="valorTotal">R$ 0,00</p>
        </div>

    </div>

    <!-- FORMULÁRIO -->
    <div class="formulario">

        <div class="form-grid">

            <input type="text" id="produto" placeholder="Nome do Produto">

            <input type="number" id="quantidade" placeholder="Quantidade">

            <input type="number" id="preco" placeholder="Preço Unitário">

            <select id="categoria">
                <option value="">Categoria</option>
                <option>Bebidas</option>
                <option>Carnes</option>
                <option>Massas</option>
                <option>Hortifruti</option>
                <option>Limpeza</option>
                <option>Outros</option>
            </select>

            <button class="btn-add" onclick="adicionarProduto()">
                ➕ Adicionar Produto
            </button>

        </div>

    </div>

    <!-- TABELA -->
    <table>

        <thead>
            <tr>
                <th>Produto</th>
                <th>Categoria</th>
                <th>Quantidade</th>
                <th>Preço</th>
                <th>Total</th>
                <th>Status</th>
                <th>Ações</th>
            </tr>
        </thead>

        <tbody id="tabelaProdutos"></tbody>

    </table>


    </div>

    <!-- CONTROLE DE PONTO -->
    <div id="controle" class="tela">

        <h1>⏰ Controle de Ponto</h1>

        <div id="relogio"></div>

        <input type="text" id="nomePonto" placeholder="Nome do funcionário">

        <input type="text" id="funcaoPonto" placeholder="Função">

        <button class="entrada" onclick="registrar('entrada')">
            Registrar Entrada
        </button>

        <button class="saida" onclick="registrar('saida')">
            Registrar Saída
        </button>

        <table>

            <thead>
                <tr>
                    <th>Nome</th>
                    <th>Função</th>
                    <th>Data</th>
                    <th>Entrada</th>
                    <th>Saída</th>
                    <th>Total (Horas)</th>
                    <th>Ação</th>
                </tr>
            </thead>

            <tbody id="tabelaPonto"></tbody>

        </table>

    </div>

    <!-- FUNCIONÁRIOS -->
    <div id="funcionarios" class="tela">

        <h1>👨‍🍳 Cadastro de Funcionários</h1>

        <input type="text" id="nomeFuncionario" placeholder="Nome">

        <input type="text" id="cargo" placeholder="Cargo">

        <input type="text" id="telefone" placeholder="Telefone">

        <input type="number" id="salario" placeholder="Salário">

        <select id="status">
            <option value="Ativo">✔️ Ativo</option>
            <option value="Desativado">❌ Desativado</option>
        </select>

        <button class="cadastrar" onclick="cadastrar()">
            Cadastrar Funcionário
        </button>

        <table>

            <thead>
                <tr>
                    <th>Nome</th>
                    <th>Cargo</th>
                    <th>Telefone</th>
                    <th>Salário</th>
                    <th>Status</th>
                    <th>Ações</th>
                </tr>
            </thead>

            <tbody id="tabelaFuncionarios"></tbody>

        </table>

    </div>

    <!-- RH -->
    <div id="rh" class="tela">

        <h1>🏢 RH</h1>
        <p>Área de RH em desenvolvimento.</p>
        🔍 Buscar funcionário...

    </div>

    <!-- MESAS -->
    <div id="mesas" class="tela">

        <h1>🪑 Controle de Mesas</h1>
        <p>Área de mesas em desenvolvimento.</p>

    </div>

    <!-- PEDIDOS -->
    <div id="pedidos" class="tela">

        <h1>🧾 Pedidos</h1>
        <p>Área de pedidos em desenvolvimento.</p>

    </div>

</div>

<script>

/* TROCAR TELAS */
function mostrarTela(id){

    let telas = document.querySelectorAll(".tela");

    telas.forEach(tela => {
        tela.classList.remove("ativa");
    });

    document.getElementById(id).classList.add("ativa");
}

/* RELÓGIO */
function atualizarRelogio(){

    const agora = new Date();

    const data = agora.toLocaleDateString();

    const hora = agora.toLocaleTimeString();

    document.getElementById("relogio").innerHTML =
        "📅 " + data + " ⏰ " + hora;
}

setInterval(atualizarRelogio, 1000);

atualizarRelogio();

/* FUNÇÕES DE DATA */
function agora(){
    return new Date();
}

function formatarHora(data){
    return data.toLocaleTimeString();
}

function formatarData(data){
    return data.toLocaleDateString();
}

/* REGISTRAR PONTO */
function registrar(tipo){

    const nome = document.getElementById("nomePonto").value;

    const funcao = document.getElementById("funcaoPonto").value;

    if(nome === ""){
        alert("Digite o nome!");
        return;
    }

    let registros = JSON.parse(localStorage.getItem("ponto")) || [];

    const dataAtual = formatarData(agora());

    const horaAtual = formatarHora(agora());

    if(tipo === "entrada"){

        registros.push({
            nome,
            funcao,
            data:dataAtual,
            entrada:horaAtual,
            saida:"",
            total:""
        });
    }

    if(tipo === "saida"){

        for(let i = registros.length - 1; i >= 0; i--){

            if(registros[i].nome === nome && registros[i].saida === ""){

                registros[i].saida = horaAtual;

                registros[i].total =
                    calcularHoras(
                        registros[i].entrada,
                        horaAtual
                    );

                break;
            }
        }
    }

    localStorage.setItem(
        "ponto",
        JSON.stringify(registros)
    );

    renderizarPonto();
}

/* CALCULAR HORAS */
function calcularHoras(entrada, saida){

    const [h1,m1,s1] = entrada.split(":").map(Number);

    const [h2,m2,s2] = saida.split(":").map(Number);

    const inicio = new Date(0,0,0,h1,m1,s1);

    const fim = new Date(0,0,0,h2,m2,s2);

    const diff = (fim - inicio) / 1000 / 60 / 60;

    return diff.toFixed(2);
}

/* DELETAR REGISTRO */
function deletar(index){

    let registros =
        JSON.parse(localStorage.getItem("ponto")) || [];

    registros.splice(index,1);

    localStorage.setItem(
        "ponto",
        JSON.stringify(registros)
    );

    renderizarPonto();
}

/* RENDERIZAR TABELA PONTO */
function renderizarPonto(){

    const tabela =
        document.getElementById("tabelaPonto");

    tabela.innerHTML = "";

    let registros =
        JSON.parse(localStorage.getItem("ponto")) || [];

    registros.forEach((r,i) => {

        tabela.innerHTML += `
            <tr>
                <td>${r.nome}</td>
                <td>${r.funcao}</td>
                <td>${r.data}</td>
                <td>${r.entrada}</td>
                <td>${r.saida}</td>
                <td>${r.total}</td>

                <td>
                    <button
                        class="delete"
                        onclick="deletar(${i})">
                        Excluir
                    </button>
                </td>
            </tr>
        `;
    });
}

renderizarPonto();

/* CARREGAR DO LOCALSTORAGE */
let funcionarios =
    JSON.parse(localStorage.getItem("funcionarios")) || [];

/* SALVAR */
function salvar(){
    localStorage.setItem(
        "funcionarios",
        JSON.stringify(funcionarios)
    );
}

/* CADASTRAR FUNCIONÁRIO */
function cadastrar(){

    let nome =
        document.getElementById(
            "nomeFuncionario"
        ).value.trim();

    let cargo =
        document.getElementById(
            "cargo"
        ).value.trim();

    let telefone =
        document.getElementById(
            "telefone"
        ).value.trim();

    let salario =
        document.getElementById(
            "salario"
        ).value;

    let status =
        document.getElementById(
            "status"
        ).value;

    if(
        nome === "" ||
        cargo === "" ||
        telefone === "" ||
        salario === ""
    ){
        alert("Preencha todos os campos!");
        return;
    }

    let tabela =
        document.getElementById(
            "tabelaFuncionarios"
        );

    let linha = document.createElement("tr");

    linha.innerHTML = `
        <td>${nome}</td>
        <td>${cargo}</td>
        <td>${telefone}</td>
        <td>R$ ${Number(salario).toFixed(2)}</td>
        <td>${status}</td>

        <td>
            <button
                class="delete"
                onclick="remover(this)">
                ❌ Excluir
            </button>
        </td>
    `;

    tabela.appendChild(linha);

    /* LIMPAR CAMPOS */
    document.getElementById( "nomeFuncionario").value = "";

    document.getElementById("cargo").value = "";

    document.getElementById("telefone").value = "";

    document.getElementById( "salario").value = "";

    document.getElementById("status").value = "Ativo";
}

/* REMOVER FUNCIONÁRIO */
function remover(botao){
    botao.parentElement.parentElement.remove();
}

/* INICIAR */
renderizar();

</script>

<script>
    let estoque =
    JSON.parse(localStorage.getItem("estoque")) || [];

/* ADICIONAR PRODUTO */
function adicionarProduto(){

    let produto =
        document.getElementById("produto").value.trim();

    let quantidade =
        document.getElementById("quantidade").value;

    let preco =
        document.getElementById("preco").value;

    let categoria =
        document.getElementById("categoria").value;

    if(
        produto === "" ||
        quantidade === "" ||
        preco === "" ||
        categoria === ""
    ){
        alert("Preencha todos os campos!");
        return;
    }

    estoque.push({
        produto,
        quantidade:Number(quantidade),
        preco:Number(preco),
        categoria
    });

    salvarDados();

    limparCampos();

    renderizarTabela();
}

/* SALVAR LOCALSTORAGE */
function salvarDados(){

    localStorage.setItem(
        "estoque",
        JSON.stringify(estoque)
    );
}

/* LIMPAR CAMPOS */
function limparCampos(){

    document.getElementById("produto").value = "";

    document.getElementById("quantidade").value = "";

    document.getElementById("preco").value = "";

    document.getElementById("categoria").value = "";
}

/* STATUS ESTOQUE */
function statusEstoque(qtd){

    if(qtd <= 5){
        return {
            texto:"BAIXO",
            classe:"baixo"
        };
    }

    if(qtd <= 15){
        return {
            texto:"MÉDIO",
            classe:"medio"
        };
    }

    return {
        texto:"ALTO",
        classe:"alto"
    };
}

/* RENDERIZAR */
function renderizarTabela(){

    let tabela =
        document.getElementById("tabelaProdutos");

    tabela.innerHTML = "";

    let totalProdutos = estoque.length;

    let baixoEstoque = 0;

    let valorTotal = 0;

    estoque.forEach((item,index)=>{

        let status =
            statusEstoque(item.quantidade);

        if(item.quantidade <= 5){
            baixoEstoque++;
        }

        let totalItem =
            item.quantidade * item.preco;

        valorTotal += totalItem;

        tabela.innerHTML += `
            <tr>

                <td>${item.produto}</td>

                <td>${item.categoria}</td>

                <td>${item.quantidade}</td>

                <td>
                    R$ ${item.preco.toFixed(2)}
                </td>

                <td>
                    R$ ${totalItem.toFixed(2)}
                </td>

                <td class="${status.classe}">
                    ${status.texto}
                </td>

                <td>

                    <button
                        class="btn-edit"
                        onclick="editarProduto(${index})">
                        ✏️
                    </button>

                    <button
                        class="btn-delete"
                        onclick="deletarProduto(${index})">
                        🗑️
                    </button>

                </td>

            </tr>
        `;
    });

    document.getElementById("totalProdutos")
        .innerText = totalProdutos;

    document.getElementById("baixoEstoque")
        .innerText = baixoEstoque;

    document.getElementById("valorTotal")
        .innerText =
            "R$ " + valorTotal.toFixed(2);
}

/* DELETAR */
function deletarProduto(index){

    if(confirm("Deseja remover este produto?")){

        estoque.splice(index,1);

        salvarDados();

        renderizarTabela();
    }
}

/* EDITAR */
function editarProduto(index){

    let item = estoque[index];

    let novoNome =
        prompt("Editar produto:", item.produto);

    let novaQtd =
        prompt("Editar quantidade:", item.quantidade);

    let novoPreco =
        prompt("Editar preço:", item.preco);

    if(
        novoNome !== null &&
        novaQtd !== null &&
        novoPreco !== null
    ){

        estoque[index].produto = novoNome;

        estoque[index].quantidade =
            Number(novaQtd);

        estoque[index].preco =
            Number(novoPreco);

        salvarDados();

        renderizarTabela();
    }
}

/* INICIAR */
renderizarTabela();

</script>

</body>
</html>