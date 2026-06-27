<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mecscop</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#0a0a0a;
color:white;
}

header{
background:#b30000;
padding:20px;
text-align:center;
}

nav{
display:flex;
justify-content:center;
gap:20px;
flex-wrap:wrap;
margin-top:15px;
}

nav a{
cursor:pointer;
font-weight:bold;
font-size:18px;
}

section{
padding:30px;
}

.hidden{
display:none;
}

.cards,.lista-servicos{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:15px;
list-style:none;
margin-top:20px;
}

.card,.lista-servicos li{
background:#111;
border:2px solid red;
padding:15px;
border-radius:10px;
cursor:pointer;
min-width:220px;
transition:.3s;
}

.card:hover,.lista-servicos li:hover{
background:red;
}

.quiz{
background:#111;
padding:25px;
border-radius:10px;
max-width:900px;
margin:auto;
}

input,select,textarea{
width:100%;
padding:12px;
margin:10px 0 20px;
}

button{
background:red;
color:white;
padding:12px 20px;
border:none;
border-radius:6px;
cursor:pointer;
}

.info{
white-space:pre-line;
line-height:1.8;
}
</style>
</head>
<body>

<header>
<h1>Mecscop</h1>

<nav>
<a onclick="mostrarPagina('inicio')">Serviços</a>
<a onclick="mostrarPagina('diagnostico')">Diagnóstico</a>
<a onclick="mostrarPagina('carros')">Carros</a>
<a onclick="mostrarPagina('dicas')">Dicas</a>
<a onclick="mostrarPagina('agendamento')">Agendamento</a>
</nav>
</header>

<!-- INICIO -->
<section id="inicio">
<h2>Sobre a Mecscop</h2>

<p class="info">
A Mecscop é uma oficina especializada em manutenção preventiva e corretiva.

Trabalhamos com:
• Motores
• Suspensão
• Freios
• Scanner
• Elétrica
• Ar-condicionado
• Radiadores
• Câmbio

Nosso foco é entregar segurança, qualidade e rapidez.
</p>

<h2>Serviços</h2>

<ul class="lista-servicos">
<li onclick="abrirServico('oleo')">Troca de óleo</li>
<li onclick="abrirServico('freio')">Freios</li>
<li onclick="abrirServico('motor')">Motor</li>
<li onclick="abrirServico('suspensao')">Suspensão</li>
<li onclick="abrirServico('injecao')">Injeção</li>
<li onclick="abrirServico('embreagem')">Embreagem</li>
<li onclick="abrirServico('radiador')">Radiador</li>
<li onclick="abrirServico('eletrica')">Elétrica</li>
<li onclick="abrirServico('scanner')">Scanner</li>
<li onclick="abrirServico('escapamento')">Escapamento</li>
<li onclick="abrirServico('alinhamento')">Alinhamento</li>
<li onclick="abrirServico('balanceamento')">Balanceamento</li>
<li onclick="abrirServico('ar')">Ar-condicionado</li>
</ul>
</section>

<section id="servico" class="hidden">
<h2 id="tituloServico"></h2>
<p id="descServico" class="info"></p>
<p id="precoServico"></p>
<button onclick="mostrarPagina('inicio')">Voltar</button>
</section>

<!-- DIAGNOSTICO -->
<section id="diagnostico" class="hidden">
<div class="quiz">
<h2>Diagnóstico Inteligente</h2>

<select id="painel">
<option>Nenhuma luz no painel</option>
<option>Luz do óleo</option>
<option>Luz do motor</option>
<option>Luz da bateria</option>
<option>Luz da temperatura</option>
</select>

<select id="barulho">
<option>Sem barulho</option>
<option>Faz barulho</option>
</select>

<select id="vibrando">
<option>Não vibra</option>
<option>Está vibrando</option>
</select>

<select id="aquecendo">
<option>Não aquece</option>
<option>Está aquecendo</option>
</select>

<select id="baixandoOleo">
<option>Óleo normal</option>
<option>Baixando óleo</option>
</select>

<select id="forca">
<option>Sem perda de força</option>
<option>Perdendo força</option>
</select>

<select id="aguaBaixa">
<option>Água normal</option>
<option>Baixando água</option>
</select>

<select id="partida">
<option>Partida normal</option>
<option>Falhando na partida</option>
</select>

<select id="consumo">
<option>Consumo normal</option>
<option>Gastando muito combustível</option>
</select>

<select id="fumaca">
<option>Sem fumaça</option>
<option>Fumaça branca</option>
<option>Fumaça preta</option>
<option>Fumaça azul</option>
</select>

<button onclick="fazerDiagnostico()">Gerar diagnóstico</button>

<p id="resultado" class="info"></p>

<button onclick="mostrarPagina('agendamento')">Agendar</button>
</div>
</section>

<!-- CARROS -->
<section id="carros" class="hidden">
<h2>Modelos e anos</h2>

<div class="cards">
<div class="card" onclick="abrirCarro('Gol G5 2010')">Gol G5 2010</div>
<div class="card" onclick="abrirCarro('Uno Vivace 2012')">Uno Vivace 2012</div>
<div class="card" onclick="abrirCarro('Onix LT 2018')">Onix LT 2018</div>
<div class="card" onclick="abrirCarro('HB20 2019')">HB20 2019</div>
<div class="card" onclick="abrirCarro('Corolla XEi 2017')">Corolla XEi 2017</div>
<div class="card" onclick="abrirCarro('Civic Touring 2020')">Civic Touring 2020</div>
<div class="card" onclick="abrirCarro('Hilux SRX 2021')">Hilux SRX 2021</div>
<div class="card" onclick="abrirCarro('Toro Volcano 2022')">Toro Volcano 2022</div>
</div>
</section>

<section id="carroInfo" class="hidden">
<h2 id="nomeCarro"></h2>
<p id="textoCarro" class="info"></p>
<button onclick="mostrarPagina('carros')">Voltar</button>
</section>

<!-- DICAS -->
<section id="dicas" class="hidden">
<h2>Dicas rápidas</h2>

<div class="cards">
<div class="card" onclick="abrirDica('oleo')">Óleo</div>
<div class="card" onclick="abrirDica('pneu')">Pneu</div>
<div class="card" onclick="abrirDica('radiador')">Radiador</div>
<div class="card" onclick="abrirDica('embreagem')">Embreagem</div>
<div class="card" onclick="abrirDica('suspensao')">Suspensão</div>
<div class="card" onclick="abrirDica('filtro')">Filtro de ar</div>
</div>
</section>

<section id="dicaInfo" class="hidden">
<h2 id="tituloDica"></h2>
<p id="textoDica" class="info"></p>
<button onclick="mostrarPagina('dicas')">Voltar</button>
</section>

<!-- AGENDAMENTO -->
<section id="agendamento" class="hidden">
<div class="quiz">
<h2>Agendamento</h2>

<input type="text" placeholder="Nome completo">
<input type="text" placeholder="Telefone">
<input type="date">
<input type="time">
<textarea placeholder="Descreva o problema do carro"></textarea>

<button>Confirmar Agendamento</button>
<button onclick="mostrarPagina('inicio')">Voltar</button>
</div>
</section>

<script>
function mostrarPagina(pagina){
document.querySelectorAll("section").forEach(sec=>sec.classList.add("hidden"));
document.getElementById(pagina).classList.remove("hidden");
}

function abrirServico(tipo){
const servicos={
oleo:["Troca de óleo","A troca de óleo mantém o motor protegido.\n\nInclui:\n• Troca do óleo\n• Troca do filtro\n• Verificação de vazamentos","R$120 a R$350"],
freio:["Freios","Sistema essencial para segurança.\n\nInclui:\n• Pastilhas\n• Discos\n• Fluido","R$200 a R$700"],
motor:["Motor","Serviços completos no motor.\n\n• Junta\n• Cabeçote\n• Pistões\n• Correias","R$500 a R$5000"],
suspensao:["Suspensão","Conforto e estabilidade.\n\n• Amortecedores\n• Buchas\n• Pivôs","R$300 a R$2500"],
injecao:["Injeção","Limpeza e scanner de sensores.","R$200 a R$1500"],
embreagem:["Embreagem","Troca de kit completo.","R$700 a R$2500"],
radiador:["Radiador","Sistema de arrefecimento completo.","R$150 a R$1200"],
eletrica:["Elétrica","Bateria, alternador e fiação.","R$150 a R$1500"],
scanner:["Scanner","Leitura de falhas eletrônicas.","R$100 a R$350"],
escapamento:["Escapamento","Catalisador, silencioso e tubos.","R$250 a R$1800"],
alinhamento:["Alinhamento","Melhora estabilidade e pneus.","R$80 a R$250"],
balanceamento:["Balanceamento","Elimina vibração nas rodas.","R$50 a R$200"],
ar:["Ar-condicionado","Carga de gás e limpeza.","R$180 a R$1200"]
};

tituloServico.innerText=servicos[tipo][0];
descServico.innerText=servicos[tipo][1];
precoServico.innerText=servicos[tipo][2];
mostrarPagina("servico");
}

function fazerDiagnostico(){
let texto="Relatório Mecscop:\n\n";

if(painel.value!="Nenhuma luz no painel") texto+="• Luz no painel indica falha importante.\n";
if(barulho.value=="Faz barulho") texto+="• Pode ser suspensão, motor ou rolamento.\n";
if(vibrando.value=="Está vibrando") texto+="• Pode ser balanceamento ou pneus.\n";
if(aquecendo.value=="Está aquecendo") texto+="• Radiador, bomba d’água ou junta podem estar com problema.\n";
if(baixandoOleo.value=="Baixando óleo") texto+="• Verificar vazamentos ou consumo interno.\n";
if(forca.value=="Perdendo força") texto+="• Pode ser embreagem, velas ou bicos.\n";
if(aguaBaixa.value=="Baixando água") texto+="• Verificar radiador e mangueiras.\n";
if(partida.value=="Falhando na partida") texto+="• Pode ser bateria, velas ou motor de partida.\n";
if(consumo.value=="Gastando muito combustível") texto+="• Pode ser filtro, bicos ou sensor lambda.\n";
if(fumaca.value=="Fumaça branca") texto+="• Possível junta do cabeçote.\n";
if(fumaca.value=="Fumaça preta") text
o+="• Excesso de combustível.\n";
if(fumaca.value=="Fumaça azul") texto+="• Motor queimando óleo.\n";

resultado.innerText=texto;
}

function abrirCarro(tipo){
const carros={
"Gol G5 2010":"Bom para cidade.\n\nPontos fortes:\n• Econômico\n• Fácil manutenção\n\nProblemas:\n• Suspensão\n• Embreagem\n\nÓleo: 5W40",
"Uno Vivace 2012":"Bom para economia.\n\nPontos fortes:\n• Baixo consumo\n• Barato\n\nProblemas:\n• Direção\n• Suspensão\n\nÓleo: 15W40",
"Onix LT 2018":"Confortável.\n\nProblemas:\n• Correia banhada a óleo\n\nÓleo: 0W20",
"HB20 2019":"Bom para cidade e viagem.\n\nÓleo: 5W30",
"Corolla XEi 2017":"Muito confiável.\n\nÓleo: 0W20",
"Civic Touring 2020":"Potente e tecnológico.\n\nÓleo: 0W20",
"Hilux SRX 2021":"Forte para trabalho.\n\nÓleo: 5W30",
"Toro Volcano 2022":"Conforto e potência.\n\nÓleo: 5W30"
};

nomeCarro.innerText=tipo;
textoCarro.innerText=carros[tipo];
mostrarPagina("carroInfo");
}

function abrirDica(tipo){
const dicas={
oleo:"Verifique sempre o nível.\n• Motor frio\n• Nível entre MIN e MAX\n• Cor ideal marrom clara",
pneu:"Verifique pressão e desgaste.\n• Troque abaixo de 1.6mm",
radiador:"Use aditivo.\n• Veja mangueiras\n• Veja vazamentos",
embreagem:"Evite ficar com pé no pedal.",
suspensao:"Barulhos indicam desgaste.",
filtro:"Filtro sujo aumenta consumo."
};

tituloDica.innerText=tipo.toUpperCase();
textoDica.innerText=dicas[tipo];
mostrarPagina("dicaInfo");
}
</script>

</body>
</html># Mecscopp
