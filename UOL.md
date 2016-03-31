<h1> ESPECIFICAÇÕES UOL</h1>

<h1>HTML5</h1>
<h2>Boas práticas</h2>
<p>Com o objetivo de diminuir problemas de implementação e veiculação disponibilizamos algumas especificações e boas práticas para o uso de HTML5:</p>
<p>O banner HTML5 deve ter todas suas referências externas como relativas. É importante lembrar que o anúncio será veiculado em páginas mais complexas e com diversos elementos, portanto é fundamental que o funcionamento do banner seja compatível com o SafeFrame do DFP.<br>
Não utilizar as boas práticas descritas neste documento pode impactar negativamente o funcionamento do anúncio e da página. Além de prejudicar a experiência do usuário. A construção da peça não pode depender de qualquer outro elemento da página ou bibliotecas javascript externas. Fontes, CSS, JS, HTML e imagens devem ser enviadas no pacote da peça.</p>
<p>Sugerimos para a criação e conversão - de peças publicitárias em HTML5 - as opções abaixo:</p>
<ul>
<li><p><strong>Doubleclick Studio Layouts:</strong>strong><br>Templates "Plug n' play", sem nenhum desenvolvimento/código. Demo - HTML5 YouTube Masthead; Desktop, Tablet e Mobile</p></li>
<li><p><strong>GWD (Google Webdesigner):</strong>strong><br>Diferentemente do Doubleclick Studio, são 100% customizáveis. Serve de ponto de partida e existem mais de 30 templates em vários formatos e tamanhos. https://support.google.com/webdesigner/
</p></li>
<li><p><strong>Vanilla HTML5:</strong><br>http://www.cssreflex.com/2014/01/vanilla-html-minimal-semantic-html5-framework.html</p></li>
<li><p><strong>Google Swiffy:</strong><br>Converte arquivos em Flash para HTML5 - https://developers.google.com/swiffy</p></li>
<li><p><strong>Flash CC</strong><br>Também pode exportar HTML5, https://helpx.adobe.com/flash/using/creating-publishing-html5-canvas-document.html.</p></li>
</ul>

<h3>Peso máximo dos anúncios</h3>
<ul class="spec"> <li><b>Desktop / Tablet:</b> 150KB</li> <li><br><b>Mobile (mWEB ou In-App)</b> 40kB</li> <li><br><b>Polite Download (somente via tag de terceiros)</b><br> Todos os arquivos subsequentes ao carregamento de peças in-page, que ultrapassam os tamanhos citados acima só poderão ser descarregados após o carregamento completo da página seguindos os limites abaixo:</li> <li>Desktop / Tablet <b>2MB</b></li> <li>Mobile (mWEB ou In-App) <b>300KB</b></li> </ul>

<h3>ClickTag</h3>
<p>Existem diversas maneiras de criar a clickTag (área de clique do anúncio) e em todas elas a página do anunciante deve abrir em uma nova janela ou aba do navegador. Abaixo temos alguns exemplos de como fazer, porém em resumo: <strong>sempre inclua a macro abaixo como URL de redirecionamento da peça.</strong>
</p>
<ul><li><table><tr><td>1</td><td><code>%%CLICK_URL_ESC%%%%DEST_URL%%</code></td></tr></table></li></ul>

<h3>JavaScript</h3>
<p>Uma forma simples de usar a variável clickTag é atribuir o href dinamicamente após o carregamento da página via JavaScript:</p>
<pre>
<code>
&lt; href="" id="clickArea" target="_blank">&gt;
&lt;script type="text/javascript">
    var clickTag = "%%CLICK_URL_ESC%%%%DEST_URL%%";
    document.getElementById('clickArea').href = clickTag;   
&lt;/script&gt;
</code>
</pre>
<p>Obs. Lembrando que a 'clickArea' precisa existir em seu HTML e seja a área clicável para redirecionamento. Além disso a chamada javascript deve vir após a existência do elemento clickArea no HTML. </p>

<h3>HTML</h3>
<p>Outra possibilidade é feito no próprio elemento HTML, conforme exemplos abaixo:</p>
<h2>Ex 1 HTML puro:</h2>
<pre><code>&lt;a href="%%CLICK_URL_ESC%%%%DEST_URL%%" target="_blank" &gt;&lt;/a&gt;</code></pre>

<h3>Ex 2 HTML + Javascript:</h3>
<pre>
<code>  
var clickTag = '%%CLICK_URL_ESC%%%%DEST_URL%%';
&lt;a href="javascript: window.open(clickTag, '_blank'); void(0)"&gt; &lt;/a &gt; </code></pre>

<h2>Ex 3 HTML + Javascript em um elemento DIV:</h2>
<code>&lt;div id="clickArea" onclick="javascript: window.open(clickTag, '_blank'); void(0)" style="cursor:pointer;" &gt;&lt;/div&gt;</code>
<p>Obs. No uso de DIV clicável, ela deve sempre exibir o cursor de 'mão'.</p>

<h3>Múltiplos Cliques</h3>
<p>Em casos de várias urls de clique dentro do mesmo anúncio, declare as variáveis de click da seguinte forma: clickTag, clickTag1, clickTag2, caso deseje utilizar via javascript.</p>
<pre><code>
var clickTag = "%%CLICK_URL_ESC%%http://www.uol.com.br"; <br>
var clickTag1 = "%%CLICK_URL_ESC%%http://economia.uol.com.br";<br>
var clickTag2 = "%%CLICK_URL_ESC%%http://esporte.uol.com.br";<br>
var clickTag3 = "%%CLICK_URL_ESC%%http://entretenimento.uol.com.br";</code></pre>

<p>Caso deseje usar em HTML puro basta adicionar as urls logo após <code>%%CLICK_URL_ESC%%</code> <br>
Ex:</p>

<pre><code>
    &lt;a href="%%CLICK_URL_ESC%%http://www.uol.com.br" target="_blank" &gt;Clique 1&lt;/a&gt;<br>
    &lt;a href="%%CLICK_URL_ESC%%%%DEST_URL%%http://economia.uol.com.br" target="_blank"&gt;Clique 2 &lt;/a&gt;<br>
    &lt;a href="%%CLICK_URL_ESC%%%%DEST_URL%%http://esporte.uol.com.br" target="_blank"&gt;Clique 3  &lt;/a&gt;<br>
    &lt;a href="%%CLICK_URL_ESC%%%%DEST_URL%%http://entretenimento.uol.com.br" target="_blank"&gt;Clique 4 &lt;/a&gt;<br>
</code></pre>

<h3>Backup</h3>

<p>Os anúncios devem servir imagem de backup para os browsers que não oferecem suporte à HTML5. 
O mesmo deve ocorrer se algum recurso externo não esteja disponível. Por exemplo no uso de XML para peças dinâmicas.</p>

<h3>Scripts</h3>
<p>Não recomendamos:</p>
<p>Usar frameworks javascript como jQuery, Prototype, YUI, Dojo, MooTools, EXTJS e AngularJS pois a probabilidade da página já utilizar um desses recursos é grande e o uso em um anúncio pode comprometer o funcionamento da página ou de outros anúncios.
Não recomendamos o uso de jQuery pois além de comprometer outras funcionalidades da página, serão adicionados 97KB e neste caso pode-se optar por zepto.js que conta com as principais funções e mesma sintaxe, porém com 9.1KB</p>

<h3>Recomendamos:</h3>
<p>Minifying, existem ferramentas online que fazem a compressão (minifying) de scripts, além disso os principais editores de código também contam com essa funcionalidade.</p>

<h3>Imagens</h3>

<p>Muitos efeitos (como o gradiente) são possíveis com o uso de CSS. (http://www.cssmatic.com/gradient-generator e http://www.w3schools.com/css/)<br>
Para uso de vetores as melhores opções são SVG (http://www.w3schools.com/svg/ e https://css-tricks.com/using-svg/ e PNG <br>
O uso de PNG e JPG como 'Save for web do Photoshop', não usam a melhor compreensão. logo experimente outras opções como TinyPNG (https://tinypng.com/ ) e TinyJPG (https://tinyjpg.com/)<br>
Obs: O uso de animações utilizando o SVG não é recomendado, para isto utilize o canvas.</p>


<h3>Fontes</h3>

<p>Fontes fora do padrão do sistema acrescentarão diversos KBs ao anúncio, podendo aumentar consideravelmente o tempo de carregamento. Sempre que possível utilize suas fontes como imagens/vetor ou defina-as em classes css especificas</p>

<p>Google Fonts: (https://developers.google.com/fonts/docs/getting_started): Biblioteca com 698 fontes para uso livre ou integrado ao Google Web Designer.</p>

<p>Fontsquirrel: (http://www.fontsquirrel.com/tools/webfont-generator ): Faz a conversão de fontes proprietárias para formatos WebFonts, reduzindo o peso.</p>

<p>Font Subsetting: http://demosthenes.info/blog/878/Slash-Page-Load-Times-With-CSS-Font-Subsetting: Técnica para reduzir peso de fontes, utilizando apenas o necessário</p>

<h3>CSS</h3>

<p>Nunca use CSS em tags globais como: body, div, span. Isso pode interferir na página e essa boa prática garante que o CSS será aplicado apenas nos elementos corretos do seu anúncio. Coloque CSS in-line ou crie seus próprios IDs ou Classes que não sejam genéricos. Por ex: container, wrapper, header, etc.</p>

<h3>Vídeo</h3>

<p>Para o uso de vídeo, recomendamos o uso do player do Youtube embedado. Além disso com algumas restrições abaixo:</p>

<h4>Autoplay:</h4>
<p>Não recomendamos o uso e não permitimos o uso sem polite download. </p>
<p>Browsers como Safari e Opera não aceitam este atributo, assim como iPad e iPhone.</p>

<h4>Poster:</h4>
<p>É importante adicionar o thumb enquanto o vídeo não é carregado.</p>

<h4>Controls:</4>
<p>Caso não desenvolva os próprios controles, este atributo é necessário para que o usuário tenha o controle do vídeo.</p>

<h4>Track:</h4>
<p>Se houver a necessidade de legenda externa nos vídeos, deve-se observar que esta tag funciona apenas nos browsers abaixo a partir das versões:</p>
- Google Chome 18+<br>
- Internet Explorer 10+<br>
- Mozilla Firefox: 31+<br>
- Safari 6+<br>
- Opera 15+<br>


<h3>Browsers Suportados</h3>

<p>Todos os browsers modernos suportam o uso de HTML5:</p>
- Chrome 40+<br>
- Firefox 35+<br>
- Internet Explorer 10+ (incluindo Edge)<br>
- Opera 20+<br>
- Safari 7.0+<br>

<p>É essencial que todos anúncios funcionem nos determinados browsers e versões.</p>

<p>Este site: https://html5test.com/results/desktop.html mostra a classificação de cada browser e versão e seu desempenho.</p>


<h1>FORMATOS DE PEÇAS</h1>

<h1> EXPANSÍVEIS</h1>
<h2>Super Banner Expansível</h2>
<p>Evite que a peça fique piscando intermitentemente.<br>
Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br>
Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.</p>
<h2>Especificações técnicas</h2>
<p>
<strong>Tamanho Inicial:</strong> 728x90 px<br>
<strong>Tamanho Expandido:</strong>até 728x300 px<br>
<strong>Sentido de Expansão: </strong>Para baixo <br>
<strong>Peso (HTML5):</strong> 150 Kb <br>
<strong>Backup (GIF/JPEG): </strong>728x90 px - 40 Kb<br><br>
<strong>Tempo de Animação:</strong> Livre <br>
<strong>Looping:</strong> Livre<br>
<strong>Som:</strong> Não pode ter som sem interação do usuário<br>
<strong>Vídeo:</strong> Aceita vídeos hospedados no Youtube<br>
<strong>Tag de Terceiro:</strong> Aceita<br.
<strong>Funcionamento:</strong> A animação deve ser construída em um único HTML. Quando o usuário passar o mouse sobre o banner (mouseOver) ele deve expandir e quando o usuario retirar o mouse (mouseOut) o banner deve retornar para o tamanho inicial (728x90).</p>

<p><img src="http://cb.i.uol.com.br/uolpublicidade/formatos/superbanner-expansivel.jpg"></p>
<dl> <dt>Exemplo</dt> <dd class="first"><a href="http://insercao.uol.com.br/galeria/galeria.php?id=2002a" target="_blank" style="height:228;">Veja a demonstração</a></dd> </dl>

<h2>Halfpage Expansível</h2>
<p>Evite que a peça fique piscando intermitentemente.<br>
Sempre que o fundo da peça for o mesmo da página coloque uma borda, principalmente se a sua peça tiver o fundo branco.<br>
Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.</p>
<h2>Especificações técnicas</h2>
<p>
<strong>Tamanho Inicial:</strong> 300x600 px<br>
<strong>Tamanho Expandido:</strong>até 940x600 px <br>
<strong>Sentido de Expansão: </strong>Para a esquerda <br>
<strong>Peso (HTML5):</strong> 150 Kb <br>
<strong>Backup (GIF/JPEG): </strong>300x600 px - 40kb <br><br>
<strong>Tempo de Animação:</strong> Livre <br>
<strong>Looping:</strong> Livre<br>
<strong>Som:</strong> Não pode ter som sem interação do usuário<br>
<strong>Vídeo:</strong> Aceita vídeos hospedados no Youtube<br>
<strong>Tag de Terceiro:</strong> Aceita<br.
<strong>Funcionamento:</strong>A animação deve ser construída em um único HTML. Quando o usuário passar o mouse sobre o banner (mouseOver) ele deve expandir e quando o usuario retirar o mouse (mouseOut) o banner deve retornar para o tamanho inicial (300x600 px).</p>

<p><img width="228" height="300" src="http://bn.imguol.com/1009/half-page-expansivel.jpg"></p>
<dl> <dt>Exemplo</dt> <dd class="first"><a href="http://insercao.uol.com.br/galeria/galeria.php?id=2002a" target="_blank" >Veja a demonstração</a></dd> </dl>

<h1>Web Alto Impacto</h1>
<h2>Barra 1280 - Intervenção</h2>

<h3>Especificações técnicas</h3>
<dd> <strong>Tamanho Inicial:</strong> 200x446 px <br> <strong>Tamanho Expandido:</strong> min 1190x446 px - max 1190x700 px <br> <strong>Sentido de Expansão :</strong> Para Esquerda e para baixo <br> <strong>Peso HTML5:</strong> Inicial 150kb | Expandido - até 2mb <br> <strong>Backup (GIF/JPEG) :</strong> 200x446 - 40 Kb<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Vídeo: </strong>Aceita vídeos hospedados no Youtube.<br> <strong>Tag de Terceiro: </strong>Aceita<br> <br> <strong>Funcionamento:</strong> A "Barra 1280 - Intervenção" deve ser construída em 2 HTMLs, sendo um HTML com o formato retraído (200x446px) e o outro HTML com o formato expandido (min 1190x446 px max 1190x700px). </dd>

<p><img src="http://cb.i.uol.com.br/uolpublicidade/formatos/barra-1280-home.jpg" </p>
<dl> <dt>Exemplo</dt> <dd class="first"><a href="http://pubads.g.doubleclick.net/gampad/preview_cookie?gct=I2BR1rrYrCAY0IjYtgUw0KSNvgWIAYCAgKDT1_r5iQE&op=set&redirect=http://uol.com.br&redirect_hash=AJlzBa0BYy4Ct3GlVYbFHaS2TRIatSm__Q&lineItemId=278109286&creativeId=99201127246" target="_blank">Veja a demonstração</a></dd> </dl>


<div class="espec"> <h3 class="title">Cutting Edge</h3> <p class="tj">O botão fechar e retrair serão inseridos pelo UOL, portanto reserve o topo superior direito da peça (55x15 pixels)</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial:</strong> 1190x70px <br> <strong>Tamanho Expandido:</strong> 1190x460px <br> <strong>Sentido de Expansão :</strong> Para baixo <br> <strong>Peso HTML5:</strong> Inicial 150kb | Expandido - Até 2mb <br> <strong>Backup (GIF/JPEG) :</strong> 1190x70px - 40kb<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Vídeo: </strong>Aceita vídeos hospedados no Youtube.<br> <strong>Tag de Terceiro: </strong>Aceita<br><br> <strong>Funcionamento:</strong> O "Cutting Edge - Expansível" deve ser construído em 2 HTMLs, sendo um HTML com o formato retraído (1190x70px) e o outro HTML com o formato expandido (1190x460px). Caso não seja um Cutting Edge Expansível, basta enviar o formato retraído (1190x70px).<br> </dd> </dl><br>
<td class="images"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/cutting-edge-fechado.jpg" style="display: inline;"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/cutting-edge-expandido.jpg" style="display: none;"> </td>

<div class="espec"> <h3 class="title">DHTML</h3> <p class="tj">A animação não pode cobrir a manchete principal, espaços publicitários, barra de navegação e não pode ter som.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho:</strong> 75.000 pixels de área (vide tabela no manual) <br> <strong>Peso HTML5:</strong> 150 kb <br> <strong>Backup (GIF/JPEG): </strong>40 kb<br> <strong>Tempo de Animação: </strong>12 segundos <br> <strong>Som: </strong>Não aceita<br> <strong>Tag de Terceiro: </strong>Sim<br> <br> <strong>Funcionamento:</strong> O DHTML deve ser construído sem o botão fechar. O mesmo será adicionado pelo UOL. O banner fechará automaticamente após 12 segundos.<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/dhtml.jpg"> </div>

<div class="espec"> <h3 class="title">DHTML Rádio UOL</h3> <p class="tj">É obrigatória a presença de um botão fechar com fácil visualização pelo usuário. A animação não pode ter som.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 588 x 414 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 40 Kb <br> <strong>Extensões Aceitas :</strong> SWF <br> <strong>Backup (GIF/JPEG) :</strong> Não<br> <strong>Tempo de Animação :</strong> 12 segundos <br> <strong>Som: </strong>Não<br> <strong>Tag de Terceiro: </strong>Apenas Contador 1x1<br> <strong>Versão Flash : </strong>Até a versão 10<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/dhtml-radio.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/22/radio-uol.html">Rádio UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Glider </h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> Ver Manual <br><br> <strong>Peça inicial: consultar formatos Home ou Capa canais (exceto Dhtml)</strong><br> <strong>Para melhor performance peça inicial no primeiro scroll.</strong><br> <strong>Tamanho Expandido:</strong> 988x500px <br> <strong>Peso HTML5:</strong> Inicial - 150kb | Final - até 2mb <br> <strong>Backup (GIF/JPEG):</strong> Sim<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/glider.jpg"> </div> <dl> <dt>Exemplo</dt> <dd class="first"><a href="http://pubads.g.doubleclick.net/gampad/preview_cookie?gct=7-nXnQz2R7gY49jzqgUw4_SosgWIAYCAgKCT0Zn0UA&amp;op=set&amp;redirect=http://economia.uol.com.br/&amp;redirect_hash=AJlzBa0zEeD2mxNv--ZS31YQRKkaKzncoA&amp;lineItemId=77213926&amp;creativeId=72180307126" target="_blank">Veja a demonstração</a></dd> </dl> <dl class="canais"> <dt>Exibido nos canais</dt> <dd><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte </a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-economia.html">UOL Economia</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-jogos.html">UOL Jogos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Jumbo Slide</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco;<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.<br> </p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 588 x 414 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a <br> <strong>Peso (kB) :</strong> 40 Kb <br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro: </strong>Apenas Contador 1x1<br> <strong>Versão Flash : </strong>Até a versão 10<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/jumbo-slide.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Logout Banner</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente.<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.<br> </p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 720 x 480 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a <br> <strong>Peso (kB) :</strong> 80 Kb <br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro: </strong>Sim<br> <strong>Versão Flash : </strong>Até a versão 10<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/logout_email-bol.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2012/10/26/bol-mail.html">BOL Mail</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Mosaico</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> Ver Manual<br><br> <strong>Peça inicial: consultar formatos Home ou Capa canais (exceto Dhtml)</strong><br> <strong>Para melhor performance peça inicial no primeiro scroll.</strong><br> <strong>Tamanho Expandido (px) :</strong> de 955x660 até 1000x660 <br> <strong>Peso (kB) :</strong> Inicial - 40kb | Final - 500 Kb <br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/mosaico_homepage.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">News Exclusiva</h3> <dl> <dt>Especificações técnicas</dt> <dd> Verificar com equipe de Shopping UOL<br><br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/news-exclusiva_shopping.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Viewport</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Peça inicial: consultar formatos Home ou Capa canais (exceto Dhtml)</strong><br> <strong>Para melhor performance peça inicial no primeiro scroll.</strong><br> <strong>Tamanho Expandido:</strong> layer no formato de 100% x 100% - área total do viewport do browser ou 1280x600 pixels. <br> <strong>Peso HTML5 :</strong> Peça inicial até 150 kb | Final até 2 mb <br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Vídeo: </strong>Aceita vídeos hospedados no Youtube.<br> <strong>Tag de Terceiro: </strong>Aceita<br> <strong>Funcionamento:</strong> A formato deve ser construído em 2 HTMLs, sendo um HTML com o formato retraído (verificar tabela de formatos) e o outro HTML com o formato expandido (1280x600 pixels). </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/retangulo-fullscreen-expandido.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Retângulo FullScreen - (Somente Flash)</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> Ver Manual<br><br> <strong>Peça inicial: consultar formatos Home ou Capa canais (exceto Dhtml)</strong><br> <strong>Para melhor performance peça inicial no primeiro scroll.</strong><br> <strong>Tamanho Expandido (px) :</strong> 1024x768 e/ou 1600x900 <br> <strong>Peso (kB) :</strong> Inicial - consultar tabela de formatos | Final - 500kb <br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/retangulo-fullscreen-expandido.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Testeira Exclusiva</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 579 x 345 <br> <strong>Peso (kB) :</strong> 100 Kb <br> <strong>Extensões Aceitas :</strong> GIF/JPEG<br> <strong>Backup (GIF/JPEG) :</strong> n/a<br> <strong>Tempo de Animação :</strong> Não <br> <strong>Looping :</strong> Não<br> <strong>Som: </strong>Não<br> <strong>Tag de Terceiro: </strong>Não<br> <strong>Versão Flash : </strong>Não pode ser em Flash<br> <strong>Frame Rate: </strong>30 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/testeira-exclusiva_shopping.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">TV Home (rotativo) BOL</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> Não pode ser flash<br><br> <strong>Tamanho Inicial (px) :</strong> 620 x 290 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a <br> <strong>Peso (kB) :</strong> 35 Kb <br> <strong>Extensões Aceitas :</strong> GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> n/a<br> <strong>Tempo de Animação :</strong> Estático <br> <strong>Looping :</strong> n/a<br> <strong>Som: </strong>Não<br> <strong>Tag de Terceiro: </strong>Apenas Contador 1x1<br> <strong>Versão Flash : </strong>n/a </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/tv-home-rotativoBOL.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/24/bol.html">BOL Homepage</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">TV Home (rotativo) UOL</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 300 x 250 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a <br> <strong>Peso (kB) :</strong> 40 Kb <br> <strong>Extensões Aceitas :</strong> SWF | GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> GIF / JPEG<br> <strong>Tempo de Animação :</strong> 12 segundos <br> <strong>Looping :</strong> Estático<br> <strong>Som: </strong>Não<br> <strong>Tag de Terceiro: </strong>Sim (Apenas tag iframe)<br> <strong>Versão Flash : </strong>Até a versão 10 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/tv-homeUOL.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Carrossel</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho (px) :</strong> 890 x 430 <br> <strong>Peso (kB) :</strong> 100 Kb <br> <strong>Extensões Aceitas :</strong> GIF / PNG<br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/carrossel.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Menu de Categoria</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho (px) :</strong> 590 x 480 <br> <strong>Peso (kB) :</strong> 100 Kb <br> <strong>Extensões Aceitas :</strong> GIF / PNG<br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/Menu-de-categoria.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Menu de Categoria Especial</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho (px) :</strong> 590 x 480 <br> <strong>Peso (kB) :</strong> 100 Kb <br> <strong>Extensões Aceitas :</strong> PNG -24 (transparente)<br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/Menu-de-categoria-especial.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Top Ofertas</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho (px) :</strong> 900 x 460 <br> <strong>Peso (kB) :</strong> 200 Kb <br> <strong>Extensões Aceitas :</strong> JPEG / PNG<br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/Top-oferta.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Especial Sazonal</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Verificar com equipe Shopping UOL</strong><br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/especial-sazonal.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<h1>PRESENCIAIS</h1>

<div class="espec"> <h3 class="title">Background</h3> <p class="tj">Não é permitido texto.<br> O Superbanner e o Background devem apresentar uma comunicação integrada, por meio de utilização das mesmas cores e imagens.<br> A logomarca do cliente ou da campanha não podem estar alinhadas com o título do canal (UOL Notícias, UOL Economia etc). </p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 1680 x altura livre com área útil de 146 pixels de cada lado <br> <strong>Peso:</strong> 80 Kb <br> <strong>Logomarcas:</strong> Se houver logomarca no background ela não pode ser alinhada com o banner <br> <strong>Extensões Aceitas :</strong> GIF / JPEG<br> <strong>Som:</strong> Não<br> <strong>Tag de Terceiro:</strong> Apenas Contador 1x1<br> <strong>Texto:</strong> Não é permitido texto. Utilize apenas cores, imagens e logomarcas<br> <strong>Recomendações (1):</strong> Ter uma comunicação visual integrada com o super banner, utilizando as mesmas cores e fundo<br> <strong>Recomendações (2):</strong> Utilize degradê nas laterais e abaixo da imagem finalizando para a mesma cor<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/BG.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br//segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Background TV UOL</h3> <p class="tj">Não é permitido texto.<br> O formato consiste em: Vídeo + retângulo médio (300x250) e Background. O retângulo médio e o background devem apresentar uma comunicação integrada, por meio de utilização das mesmas cores e imagens.<br> A logomarca do cliente ou da campanha não podem estar alinhadas com o título do canal (UOL Notícias, UOL Economia etc). </p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 1680 x altura livre com área útil de 146 pixels de cada lado <br> <strong>Peso:</strong> 80 Kb <br> <strong>Logomarcas:</strong> Se houver logomarca no background ela não pode ser alinhada com o banner <br> <strong>Extensões Aceitas :</strong> GIF / JPEG<br> <strong>Som:</strong> Não<br> <strong>Tag de Terceiro:</strong> Apenas Contador 1x1<br> <strong>Texto:</strong> Não é permitido texto. Utilize apenas cores, imagens e logomarcas<br> <strong>Recomendações (1):</strong> Ter uma comunicação visual integrada com o retângulo médio, utilizando as mesmas cores e fundo<br> <strong>Recomendações (2):</strong> Utilize degradê nas laterais e abaixo da imagem finalizando para a mesma cor<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/guide-bg-tvuol_thumb.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br//segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Patrocínio Canais</h3> <p class="tj">A peça não pode piscar intermitentemente <br> Deve ter fundo branco</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 120 x 35<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso HTML5: </strong> 20 Kb <br> <strong>Backup (GIF/JPEG): </strong> 5kb<br> <strong>Tempo de Animação :</strong> 8 segundos<br> <strong>Looping :</strong> Não<br> <strong>Som:</strong> Não <br> <strong>Som:</strong> Não <br> <strong>Tag de Terceiro:</strong> Aceita<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/Patrocinio-Canais.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> <dd><a href="http://publicidade.uol.com.br//segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Patrocínio Gols</h3> <p class="tj">Roda apenas no placar de texto dos gols dos campeonatos. Ao acontecer um gol, o banner é chamado.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 175 x 80<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 5 Kb <br> <strong>Extensões Aceitas :</strong> GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Não<br> <strong>Tempo de Animação :</strong> Estático<br> <strong>Looping :</strong> Não<br> <strong>Som:</strong> Não<br> <strong>Tag de Terceiro:</strong> Não<br> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/patrocinio-gols.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/03/22/placar-uol.html">Placar UOL</a></dd> </dl> </div>

<h1>TRADICIONAIS</h1>

<div class="espec"> <h3 class="title">Barra 1280</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente.<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 200 x 446<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 40 Kb<br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som:</strong> Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro :</strong> Sim<br> <strong>Versão Flash :</strong> Até a versão 10<br> <strong>Sugestão de Frame Rate:</strong> 12 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/barra-1280-home.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/03/08/radar-de-desconto.html">Radar de Descontos</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Retângulo</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente.<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 300 x 250<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 40 Kb<br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som:</strong> Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro :</strong> Sim<br> <strong>Versão Flash :</strong> Até a versão 10<br> <strong>Sugestão de Frame Rate:</strong> 12 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/retangulo.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="#"></a><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Super Banner</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente.<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.</p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <br> <strong>Tamanho Inicial (px) :</strong> 728 x 90<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 40 Kb<br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som:</strong> Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro :</strong> Sim<br> <strong>Versão Flash :</strong> Até a versão 10<br> <strong>Sugestão de Frame Rate:</strong> 12 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/superbanner.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/03/08/shopping-uol.html">Shopping UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Half Page</h3> <p class="tj"> Evite que a peça fique piscando intermitentemente.<br> Sempre que o fundo da peça for o mesmo da página coloque um fio de contorno, principalmente se a sua peça tiver o fundo branco.<br> Todas as peças são publicadas por padrão com o fundo transparente, caso você não queira que a peça fique com esta característica coloque um objeto de fundo.<br> </p><br> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 300 x 600<br> <strong>Tamanho Expandido (px) :</strong> n/a<br> <strong>Sentido de Expansão :</strong> n/a<br> <strong>Peso (kB) :</strong> 40 Kb<br> <strong>Extensões Aceitas :</strong> SWF / GIF / JPEG<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som:</strong> Não<br> <strong>Tag de Terceiro :</strong> Sim<br> <strong>Versão Flash :</strong> Até a versão 10<br> <strong>Sugestão de Frame Rate:</strong> 12 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/half-page.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-economia.html">UOL Economia</a></dd> </dl> </div>


<h1>VIDEO</h1>
<div class="espec"> <h3 class="title">Retângulo com Vídeo</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 300 x 250 <br> <strong>Tamanho Expandido (px) :</strong> n/a <br> <strong>Sentido de Expansão :</strong> n/a <br> <strong>Peso (kB) :</strong> 40 Kb + Vídeo (100 Mb) <br> <strong>Extensões Aceitas :</strong> Peça: SWF / GIF / JPEG - Vídeo: AVI / DIVX / DV / MOV / QT / MPEG / MPG / MP4 / ASF / WMV e FLV"<br> <strong>Backup (GIF/JPEG) :</strong> Sim<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Tag de Terceiro: </strong>Apenas Contador 1x1<br> <strong>Versão Flash : </strong>Até a versão 10<br> <strong>Sugestão de Frame Rate: </strong>12 </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/retangulo-com-video.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/02/15/uol-home-page.html">UOL Homepage</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-educacao.html">UOL Educação</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">TV UOL</h3> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Ver manual</strong> </dd> </dl> <div class="gallery single"> <img src="http://cb.i.uol.com.br/uolpublicidade/formatos/video_2.0.jpg"> </div> <dl class="canais"> <dt>Exibido nos canais</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/22/tv-uol.html/">TV UOL</a></dd> </dl> </div>

<div class="espec"> <h3 class="title">Background TV UOL</h3> <p class="tj">Só são permitidas: cores, imagens e logomarca. Não é permitido texto.<br> O retângulo médio e o background devem apresentar uma comunicação integrada, por meio de utilização das mesmas cores e imagens.<br> A logomarca do cliente ou da campanha não podem estar alinhadas com o título do canal (UOL Notícias, UOL Economia etc). </p> <dl class="doc"> <dt>Especificações técnicas</dt> <dd> <strong>Tamanho Inicial (px) :</strong> 1680 x altura livre com área útil de 146 pixels de cada lado <br> <strong>Peso (kB) :</strong> 80 Kb <br> <strong>Logomarcas:</strong> Se houver logomarca no background ela não pode ser alinhada com o banner <br> <strong>Extensões Aceitas :</strong> GIF / JPEG<br> <strong>Som:</strong> Não<br> <strong>Tag de Terceiro:</strong> Apenas Contador 1x1<br> <strong>Versão Flash :</strong> Não pode ser em Flash<br> <strong>Texto:</strong> Não é permitido texto. Utilize apenas cores, imagens e logomarcas<br> <strong>Recomendações (1):</strong> Ter uma comunicação visual integrada com o retângulo médio, utilizando as mesmas cores e fundo<br> <strong>Recomendações (2):</strong> Utilize degradê nas laterais e abaixo da imagem finalizando para a mesma cor<br> </dd> </dl> <div class="gallery single"> <img src="http://bn.imguol.com/uolpublicidade/formatos/guide-bg-tvuol_thumb.jpg"> </div> <dl class="canais"> <dt>Exibido no canal</dt> <dd class="first"><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-noticias.html">UOL Notícias</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/21/uol-esporte.html">UOL Esporte</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento.html">UOL Entretenimento</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-mulher.html">UOL Mulher</a></dd> <dd><a href="http://publicidade.uol.com.br/segmento/2013/01/22/uol-entretenimento-musica.html">UOL Música</a></dd> <dd><a href="http://publicidade.uol.com.br//segmento/2013/02/15/uol-jogos.html">UOL Jogos</a></dd> </dl> <div class="more clearfix"> <dl> <dt>Manual</dt> <dd class="first"><a href="http://publicidade.uol.com.br/manuais/background-tvuol/background.html" class="manual">Veja especificação completa</a></dd> </dl> </div> </div>
