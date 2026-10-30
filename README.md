
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Escolha sua estrela | Interact</title>
<style>
*{box-sizing:border-box}
body{margin:0;min-height:100vh;font-family:Arial,sans-serif;color:white;background:radial-gradient(ellipse at 50% 0%,#344778,#18264b 52%,#0b1228);display:flex;justify-content:center;align-items:center;padding:20px}
main{width:100%;max-width:520px;text-align:center;padding:28px 20px;border:1px solid #ffffff25;border-radius:25px;background:#ffffff09}
.eyebrow{font-size:11px;letter-spacing:4px;color:#d9cafa}
h1{font:36px Georgia,serif;margin:20px 0 12px}
.intro{font:15px/1.7 Georgia,serif;color:#d7def2}
.skyline{font-size:28px;color:#f5dfad;margin:22px}
h2{font:23px Georgia,serif}
.sub{font-size:13px;line-height:1.6;color:#cbd4ed}
.moods{display:grid;grid-template-columns:1fr 1fr;gap:10px}
button{cursor:pointer;color:white}
.mood{border:1px solid #ffffff30;background:#ffffff12;border-radius:15px;padding:16px 8px;min-height:85px;font-size:14px}
.mood:active,.star:active{background:#9e8bc0}
.stars{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;max-width:310px;margin:20px auto}
.star{height:65px;border-radius:15px;background:#ffffff12;border:1px solid #ffffff25;color:#f6dfa7;font-size:32px}
.message{margin-top:20px;padding:22px 18px;border-radius:19px;background:#ffffff15;border:1px solid #ffffff35;text-align:left}
.message h2{text-align:center}
.message p{font:16px/1.8 Georgia,serif;color:#f0eff9}
.label{text-align:center;font-size:11px;letter-spacing:3px;color:#d5c6ff}
.heart{text-align:center;border-top:1px solid #ffffff30;margin-top:17px;padding-top:14px;color:#d7c9f5;font-size:12px}
.actions{display:flex;justify-content:center;gap:9px;flex-wrap:wrap;margin-top:18px}
.action{border:1px solid #ffffff35;background:#ffffff18;padding:12px 18px;border-radius:30px;font-size:13px}
.primary{background:#e8dafa;color:#202647;border:0;font-weight:bold}
footer{border-top:1px solid #ffffff20;margin-top:25px;padding-top:16px;font-size:11px;line-height:1.8;color:#b7c2e0}
.hidden{display:none!important}
</style>
</head>
<body>
<main>
<div class="eyebrow">✦ INTERACT APRESENTA ✦</div>
<h1>Escolha sua estrela</h1>
<p class="intro">Um pequeno espaço para respirar, refletir e lembrar que você merece cuidado.</p>
<div class="skyline">✧ ⋆ ✦ ⋆ ✧</div>

<section id="step1">
<h2>O que você gostaria de receber hoje?</h2>
<p class="sub">Escolha a mensagem que mais combina com o que você gostaria de receber agora.</p>
<div class="moods">
<button class="mood" data-mood="acolhimento">♡<br>Um pouco de acolhimento</button>
<button class="mood" data-mood="cansaco">☁<br>Estou precisando de uma pausa</button>
<button class="mood" data-mood="coragem">✧<br>Preciso de coragem</button>
<button class="mood" data-mood="reflexao">☆<br>Quero refletir</button>
</div>
</section>

<section id="step2" class="hidden">
<h2>Agora escolha uma estrela...</h2>
<p class="sub">Cada uma guarda uma mensagem preparada para você.</p>
<div class="stars" id="stars"></div>
<p class="sub">Toque em qualquer estrela para descobrir sua mensagem.</p>
</section>

<section id="result" class="message hidden" aria-live="polite">
<div style="text-align:center;font-size:30px;color:#f6dfaa">✧</div>
<div class="label">UMA MENSAGEM PARA VOCÊ</div>
<h2 id="messageTitle"></h2>
<p id="messageText"></p>
<div class="heart">♡ Cuide de você. Você importa.</div>
</section>

<div class="actions">
<button id="back" class="action hidden">← Voltar</button>
<button id="again" class="action primary hidden">Escolher outra estrela ✦</button>
<button id="home" class="action hidden">Recomeçar</button>
</div>
<footer>SMI 2026 · Iluminando Caminhos<br>Saúde mental também é cuidado. ✨</footer>
</main>

<script>
const data={
acolhimento:[
["Seus sentimentos importam","Seus sentimentos merecem ser respeitados, mesmo quando você não consegue explicar exatamente o que está sentindo. Não existe uma maneira certa de passar por todos os dias. Você pode sentir, conversar, mudar de ideia e pedir apoio. Não diminua o que está vivendo só porque alguém talvez não entenda. Você merece ser ouvido com carinho."],
["Você não precisa enfrentar tudo sozinho","Às vezes, a gente tenta resolver tudo por conta própria e esquece que pode contar com outras pessoas. Conversar com alguém de confiança não é um sinal de fraqueza. É uma forma de cuidado. Você merece ter por perto pessoas que escutem sem julgar."],
["Seja gentil consigo","Você provavelmente oferece compreensão às pessoas de quem gosta. Tente oferecer um pouco dessa mesma compreensão a si. Você também está aprendendo, crescendo e descobrindo caminhos. Não precisa ter todas as respostas agora."]
],
cansaco:[
["Descansar também é importante","Você não precisa transformar todos os momentos em produtividade. Fazer uma pausa, respeitar seus limites e ter tempo para simplesmente existir também fazem parte de uma rotina saudável. Seu valor não depende de quantas coisas você consegue realizar em um dia."],
["Vá no seu próprio ritmo","Nem todo mundo percorre o mesmo caminho na mesma velocidade. Comparar sua jornada com a de outras pessoas pode fazer você esquecer o quanto já caminhou. Dê um passo de cada vez. Hoje, fazer o possível já pode ser suficiente."],
["Permita-se respirar","Talvez hoje você precise de um momento mais tranquilo. Se puder, afaste-se um pouquinho das cobranças, beba água, escute uma música de que gosta ou converse com alguém querido. Pequenos momentos de cuidado também contam."]
],
coragem:[
["Você não precisa ser perfeito","Errar, recomeçar e não saber o que fazer fazem parte da experiência de aprender. Você não precisa acertar sempre para merecer reconhecimento e carinho. Permita-se tentar, descobrir e crescer sem exigir perfeição de si."],
["Um passo de cada vez","Grandes mudanças não acontecem necessariamente de uma só vez. Às vezes, a coragem está em dar um pequeno passo, conversar sobre algo difícil ou aceitar ajuda. Reconheça suas pequenas conquistas. Elas também merecem ser celebradas."],
["Sua história continua","Um momento difícil não resume quem você é e nem determina tudo o que ainda pode viver. Existem novas experiências, aprendizados e encontros pela frente. Você merece dar a si mesmo a oportunidade de descobrir o que vem depois."]
],
reflexao:[
["Como você tem cuidado de si?","Na correria dos compromissos, estudos e responsabilidades, é fácil esquecer de perguntar como estamos de verdade. Que tal reservar alguns minutos para pensar no que tem feito bem a você e no que poderia mudar? Cuidar da saúde mental também começa com escuta e atenção."],
["Você merece ser ouvido","Pense em alguém com quem você se sente à vontade para conversar. Manter relações em que existe respeito, confiança e acolhimento faz diferença. E lembre-se: você também pode ser essa pessoa que escuta e acolhe alguém."],
["Pequenos cuidados fazem diferença","Uma conversa, uma pausa, um passeio, um hobby ou um momento com pessoas queridas podem trazer leveza à rotina. Não existe uma fórmula única para cuidar da saúde mental. Descubra quais atitudes fazem sentido para você."]
]};

const $=id=>document.getElementById(id);
let mood="",last=-1;

function show(id){
["step1","step2","result"].forEach(x=>$(x).classList.toggle("hidden",x!==id));
$("back").classList.toggle("hidden",id!=="step2");
$("again").classList.toggle("hidden",id!=="result");
$("home").classList.toggle("hidden",id!=="result");
}

document.querySelectorAll(".mood").forEach(b=>{
b.addEventListener("click",()=>{
mood=b.dataset.mood;
last=-1;
$("stars").innerHTML="";
for(let i=0;i<8;i++){
let s=document.createElement("button");
s.className="star";
s.textContent=["✦","✧","★","⋆","✶","✧","✦","☆"][i];
s.setAttribute("aria-label","Escolher estrela "+(i+1));
s.addEventListener("click",()=>{
let arr=data[mood],n;
do{n=Math.floor(Math.random()*arr.length)}while(arr.length>1&&n===last);
last=n;
$("messageTitle").textContent=arr[n][0];
$("messageText").textContent=arr[n][1];
show("result");
});
$("stars").appendChild(s);
}
show("step2");
});
});

$("back").onclick=()=>show("step1");
$("again").onclick=()=>show("step2");
$("home").onclick=()=>{
mood="";
last=-1;
show("step1");
};
</script>
</body>
</html>

