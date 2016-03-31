<h2>I - Formatos de publicidade HTML5 aceitos na Globo.com</h2>

<p>A Globo.com suporta várias formas de veiculação de HTML5, cada uma
delas possuem suas vantagens e desvantagens e foram definidas com
base em padrões internacionais, bem como nas possibilidades do
adserver da Globo.com<br>
A Globo.com se dá o direito de avaliar e pausar peças em caso de não
cumprimento das especificações deste guia, ou por problemas de
performance da peça.<br>

<h3>1. Tags de terceiros</h3>
<p>Aceitamos tags de adservers parceiros, com peças produzidas
em HTML5, desde que as especificações deste guia sejam
respeitadas. </p>
<p>Toda tag de terceiro é pré-avaliada pela equipe da Globo.com,
entretanto esses criativos podem sofrer alterações durante a
veiculação, por estarem hospedadas em um terceiro. Por este
motivo, uma pré-aprovarão da peça não é garantia de que a peça
não possa ser pausada durante uma veiculação.</p>

<h3>2. Doubleclick Campaign Manager (DCM) tags</h3>
<p>Da mesma forma que aceitamos tags de adservers parceiros,
com peças produzidas em HTML5, aceitamos tags do DCM,
desde que as especificações deste guia sejam respeitadas. </p>

<h3>3. Criativos com HTML5 completo (selfcontained)</h3>
<p>Um único código HTML5, sem nenhum asset necessário.
Lembrando que os assets também não podem estar em links
externos</p>

<h3>4. Pacote (zip) HTML5 para hospedagem no adserver da Globo.com</h3>
<p>Em um único arquivo Zip, contendo o HTML principal e os assets
necessários, como CSS, JS, IMAGENS</p>
<p>Este modelo, não exige que o anunciante contrate um adserver
terceiro, basta enviar o arquivo .zip, com o html principal e os
asset que a Globo.com hospeda o criativo.</p>

<h2>II. Guia e especificações para envio na forma:
Pacote (zip) HTML5 para hospedagem no
adserver da Globo.com
</h2>

<h3>Peso do criativo</h3>
<p><strong>Premissas:</strong> <br>
Carregamento normal: Quando os asset são carregados imediatamente ao
carregamento da peça.<br>
Polite: Os assets do criativo são carregados após o carregamento da página
(peça principal).</p>

<h3>Peso máximo</h3>
<ul>
    <li>Tamanho máximo de peças comuns:<br>
Desktop: 150kB<br>
Mobile (mWeb e In-App): 60kB</li>
    <li>Tamanho máximo de peças polite<br>
Desktop: pré-carregamento 40kB, do total de 400kB após o
load da página<br>
Mobile (mWeb e In-App): pré-carregamento 40kB, do total
de 200kB após o load da página
</li>

<p>O que é considerado na contabilização do peso total?
Para chegar no peso total, é considerada a somatória dos pesos de todos
os arquivos do zip descompactado, bem como os arquivos externos
permitidos por este guia, como Google fontes, por exemplo.
</p>

<h2>Fontes</h2>

<p>Que tipo de fontes são suportadas? Recomendamos o uso de Fontes
de sistema. Para casos onde se faça necessário o uso de fontes que
não são de sistemas, deve-se usar o Google Fonts, mas sempre colocando fontes de sistema como backup</p>
</ul>

<h2>Estrutura</h2>
<ul>
    <li><p>Estrutura do HTML e seus assets
Os assets devem estar no mesmo nível do html principal, ou seja,
não devem existir pastas organizando os assets</p></li>
<li><p>Como enviar o pacote para a Globo.com?
Basta criar um arquivo zip, que contempla todos os arquivos
necessário para o criativo.</p></li>
</ul>

<h2>Arquivos externos</h2>
<ul>
    <li>Quais links externos são permitidos?</li>
        <ul>
            <li>URL de destino</li>
            <li>Pixel contadores</li>
            <li>Link para fontes externas (Google Fonts)</li>
        </ul>
    <li>Cosntrução de links externos através de javascript</li>
        <ul><li>Não é permitido</li></ul>
</ul>

<h2>Assets</h2>
<h3>Quais tipos de assets são suportados?</h3>
<p>Imagens<br>
aceitos: .jpg .png .gif<br>
não aceitos: .svg
</p><br>
<p>Vídeos</p>
<p>Arquivos de vídeos só podem ser carregados a partir do
acionamento do play pelo usuário <br>
O link para os arquivos devem ser para servidores de
streaming, ou servidores externos, quando ultrapassam o
limite de peso do pacote do criativo<br>
Os arquivos de vídeo exigem uma extensão .mp4. O
formato mp4 maximiza a compatibilidade entre o
navegador e os dispositivos. O codec deve ser H.264.
</p>

<p>Fontes</p><br>
Aceitos: Google Fonts (link)<br>
não aceitos: fontes como assets<br>

<p>CSS(.css)</p>
<p>Javascript(.js)</p>

<h2>Javascript</h2>
<p>Arquivos .js externos</p>
<p>Não é permitido ter referências a arquivos js e bibliotecas
externas, apenas aos assets do pacote<br>
Bibliotecas<br>
Os limites de peso devem ser respeitados, portanto
recomendamos que, se for extremamente necessário,
usem bibliotecas simplificadas, que tenham apenas os
recursos necessários para o funcionamento da peça <br>
Para formatos In-App a Globo.com não dá suporte a
mraid.js</p>

<h1>MACROS DE CLICK</h1>

<p>Aceitaremos três métodos:</p>

<p>1. A macro de clique que adotamos é uma declaração de uma
variável chamada clickTag:</p>
<code>
&lt;script type="text/javascript" &gt;
var clickTag =  "%%CLICK_URL_ESC%%%%DEST_URL%%;"   
&lt;/script&gt;</code>

<p>2. Para peças com múltiplos cliques, deve-se declarar a variável
clickTag e usá-la na construção dos links da peça
</p>
<code>
&lt;script type="text/javascript" &gt;
var clickTag =  "%%CLICK_URL_ESC%%";

document,getElementById("link_destino1").href = clickTag+"http://exemplo.com/link1"
document,getElementById("link_destino2").href = clickTag+"http://exemplo.com/link2"
&lt;/script&gt;</code>

<p>3. Se nenhuma das opções acima forem adotadas, assim como
qualquer tag, peças HTML5 devem possuir as macros de clique
do DFP, caso contrário, será usado o Override.
</p>

<h1>IV. Pixels Contadores</h1>
<p>Pixels contadores devem ser enviados separadamente, pois serão
adequadamente inseridos no código de forma automatizada, no final do
documento HTML</p>

<h1>V. Boas práticas</h1>
<p><strong>1. Animações</strong></p>
<p>Evite ao máximo o uso de javascripts para animações /
transições, dando sempre preferência ao recurso de
transições do CSS</p>
<p><strong>2. Fontes</strong></p>
<p>Para textos estáticos use o recurso de redução de peso
das fontes do Google Fonts (ver item Fontes)</p>
<p><strong>3. Javascripts</strong></p>
<p>Evite recursos que elevem o processamento da máquina
do usuário, como loopings, Intervals, efeitos, etc. Isso
prejudica a experiência do usuário e a navegação nas
páginas da Globo.com</p>
<p>jQuery não é recomendado para anúncios HTML5 pelas
seguintes razões:</p>
<p>Desempenho reduzido em dispositivos móveis por
causa da dependência de animações baseadas em
tempo.</p>
<p>Ponderação desnecessária de arquivos: a maioria
das funcionalidades da biblioteca não é necessária.
 Como alternativa, procure bibliotecas mais leves, como
a zepto.js</p>

<h1>FORMATOS RICHMEDIA</h1>

<h2>SUPER LEADERBOARD FULLSCREEN</h2>

<p>Peso:
12 kb na peça de pré
-
carregamento + 300 kb da peça principal
+ 2Mb do vídeo.</p>

<p>Dimensões: 
− <p></p>
Antes da interação as dimensões da peça são de 970 
x 90px. <p></p>
−
Após o clique do usuário, a peça terá a dimensão da
 tela (
fullscreen
), mas a área útil de 
criação terá a dimensão de até 1024 x 768px. </p>

<p>Tempo:</p> 
<p>−
A peça expandida terá um tempo máximo de animação d
e 15s.  <br>
−
Caso tenha vídeo, a peça terá um tempo total de 15s
 mais o tempo de duração do vídeo.</p> 

 <p><strong>IMPORTANTE: Durante o carregamento da página só é p
ermitido o carregamento de 52 kb de 
arquivos ‘terceiros”, sendo os 12 kb da peça pré + c
ódigos. Após o carregamento da página é 
carregada a peça principal + códigos.</strong></p>

<p>Vídeo/Áudio:
 O vídeo poderá iniciar automaticamente com o áudio
 desativado, sendo ativado por 
ação do usuário através de um clique. Caso o vídeo 
seja acionado por clique do usuário, o áudio já 
poderá vir ativado. </p>

<p>Orientações Gerais: </p>

<p>−
A opção desta rich media pode não estar disponível 
para determinados formatos e sites. 
Consulte sempre a Opec para saber se há alguma rest
rição para o canal escolhido. <br>
−
A peça poderá ser em Flash 9 ou superior. <br>
−
Tendo como base estudos feitos acerca do consumo de
 CPU, a Globo.com recomenda o uso 
de 18fps.</p>

<p>Orientações específicas para esta peça: </p>
<p>−
O prazo para testes funcionais desta peça é de 
16 horas úteis<br>
. 
−
Caso a peça tenha o fundo na cor branca, será neces
sária uma borda de 1 pixel de 
espessura na cor 
#e8e8e8<br>
.  
−
O botão fechar deve estar presente no canto superio
r direito da peça em ambos os 
momentos, ou seja, antes e depois da interação. </p>



<h2>
SUPER LEADERBOARD EXPANSÍVEL
</h2>

<p><strong>
	Peso
</strong>
 12 kb na peça de pré
-
carregamento + 300 kb da peça principal
+ 2Mb do vídeo.
</p>

<p><strong>
	Dimensões: 
</strong><br>
Antes da interação as dimensões são as mesmas do Su
per Leaderboard  970 x 90px. 
<br>
Após o clique do usuário, a peça expandida terá 970
 X 250px
</p>

<p><strong>
IMPORTANTE: Durante o carregamento da página só é p
ermitido o carregamento de 52 kb de 
arquivos  “terceiros”, sendo os 12 kb da peça pré + c
ódigos. Após o carregamento da página é 
carregada a peça principal + códigos.
</strong></p>

<p><strong>
	<!-- especificações add -->Especificações Adicionais:
</strong></p>

<p>
	Vídeo/Áudio:
 Após a interação o vídeo poderá iniciar automatica
mente com o áudio desativado, 
sendo ativado por ação do usuário através de um cli
que. Caso o vídeo seja acionado por clique do 
usuário, o áudio já poderá vir ativado. 	<br>
	Caso a peça tenha o fundo na cor branca, será neces
sária uma borda de 1 pixel de espessura na 
cor 
#e8e8e8
. 
</p>

<p><strong>
	Orientações Gerais:
</strong><br>
A opção desta rich media pode não estar disponível 
para determinados formatos e sites. 
Consulte sempre a Opec para saber se há alguma rest
rição para o canal escolhido. 
<br>
A peça poderá ser em Flash 9 ou superior. 
<br>
Tendo como base estudos feitos acerca do consumo de
 CPU, a Globo.com recomenda o uso 
de 18fps.
</p>

<p><strong>
Orientações específicas para esta peça: 
</strong><br>O prazo para testes funcionais desta peça é de 
16 horas úteis
. <br>
O botão fechar deve estar presente no canto superio
r direito da peça depois da interação
</p>
