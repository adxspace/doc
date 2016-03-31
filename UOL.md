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

<h2>Peso máximo dos anúncios</h2>
<ul class="spec"> <li><b>Desktop / Tablet:</b> 150KB</li> <li><br><b>Mobile (mWEB ou In-App)</b> 40kB</li> <li><br><b>Polite Download (somente via tag de terceiros)</b><br> Todos os arquivos subsequentes ao carregamento de peças in-page, que ultrapassam os tamanhos citados acima só poderão ser descarregados após o carregamento completo da página seguindos os limites abaixo:</li> <li>Desktop / Tablet <b>2MB</b></li> <li>Mobile (mWEB ou In-App) <b>300KB</b></li> </ul>

<h2>ClickTag</h2>
<p>Existem diversas maneiras de criar a clickTag (área de clique do anúncio) e em todas elas a página do anunciante deve abrir em uma nova janela ou aba do navegador. Abaixo temos alguns exemplos de como fazer, porém em resumo: <strong>sempre inclua a macro abaixo como URL de redirecionamento da peça.</strong>
</p>
<ul><li><table><tr><td>1</td><td><code>%%CLICK_URL_ESC%%%%DEST_URL%%</code></td></tr></table></li></ul>

<h2>JavaScript</h2>
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

<h2>HTML</h2>
<p>Outra possibilidade é feito no próprio elemento HTML, conforme exemplos abaixo:</p>
<h2>Ex 1 HTML puro:</h2>
<pre><code>&lt;a href="%%CLICK_URL_ESC%%%%DEST_URL%%" target="_blank" &gt;&lt;/a&gt;</code></pre>

<h2>Ex 2 HTML + Javascript:</h2>
<pre>
<code>  
var clickTag = '%%CLICK_URL_ESC%%%%DEST_URL%%';
&lt;a href="javascript: window.open(clickTag, '_blank'); void(0)"&gt; &lt;/a &gt; </code></pre>

<h2>Ex 3 HTML + Javascript em um elemento DIV:</h2>
<code>&lt;div id="clickArea" onclick="javascript: window.open(clickTag, '_blank'); void(0)" style="cursor:pointer;" &gt;&lt;/div&gt;</code>
<p>Obs. No uso de DIV clicável, ela deve sempre exibir o cursor de 'mão'.</p>

<h2>Múltiplos Cliques</h2>
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

<h2>Backup</h2>

<p>Os anúncios devem servir imagem de backup para os browsers que não oferecem suporte à HTML5. 
O mesmo deve ocorrer se algum recurso externo não esteja disponível. Por exemplo no uso de XML para peças dinâmicas.</p>

<h2>Scripts</h2>
<p>Não recomendamos:</p>
<p>Usar frameworks javascript como jQuery, Prototype, YUI, Dojo, MooTools, EXTJS e AngularJS pois a probabilidade da página já utilizar um desses recursos é grande e o uso em um anúncio pode comprometer o funcionamento da página ou de outros anúncios.
Não recomendamos o uso de jQuery pois além de comprometer outras funcionalidades da página, serão adicionados 97KB e neste caso pode-se optar por zepto.js que conta com as principais funções e mesma sintaxe, porém com 9.1KB</p>

<h2>Recomendamos:</h2>
<p>Minifying, existem ferramentas online que fazem a compressão (minifying) de scripts, além disso os principais editores de código também contam com essa funcionalidade.</p>

<h2>Imagens</h2>

<p>Muitos efeitos (como o gradiente) são possíveis com o uso de CSS. (http://www.cssmatic.com/gradient-generator e http://www.w3schools.com/css/)<br>
Para uso de vetores as melhores opções são SVG (http://www.w3schools.com/svg/ e https://css-tricks.com/using-svg/ e PNG <br>
O uso de PNG e JPG como 'Save for web do Photoshop', não usam a melhor compreensão. logo experimente outras opções como TinyPNG (https://tinypng.com/ ) e TinyJPG (https://tinyjpg.com/)<br>
Obs: O uso de animações utilizando o SVG não é recomendado, para isto utilize o canvas.</p>


<h2>Fontes</h2>

<p>Fontes fora do padrão do sistema acrescentarão diversos KBs ao anúncio, podendo aumentar consideravelmente o tempo de carregamento. Sempre que possível utilize suas fontes como imagens/vetor ou defina-as em classes css especificas</p>

<p>Google Fonts: (https://developers.google.com/fonts/docs/getting_started): Biblioteca com 698 fontes para uso livre ou integrado ao Google Web Designer.</p>

<p>Fontsquirrel: (http://www.fontsquirrel.com/tools/webfont-generator ): Faz a conversão de fontes proprietárias para formatos WebFonts, reduzindo o peso.</p>

<p>Font Subsetting: http://demosthenes.info/blog/878/Slash-Page-Load-Times-With-CSS-Font-Subsetting: Técnica para reduzir peso de fontes, utilizando apenas o necessário</p>

<h2>CSS</h2>

<p>Nunca use CSS em tags globais como: body, div, span. Isso pode interferir na página e essa boa prática garante que o CSS será aplicado apenas nos elementos corretos do seu anúncio. Coloque CSS in-line ou crie seus próprios IDs ou Classes que não sejam genéricos. Por ex: container, wrapper, header, etc.</p>

<h2>Vídeo</h2>

<p>Para o uso de vídeo, recomendamos o uso do player do Youtube embedado. Além disso com algumas restrições abaixo:</p>

<h3>Autoplay:</h3>
<p>Não recomendamos o uso e não permitimos o uso sem polite download. </p>
<p>Browsers como Safari e Opera não aceitam este atributo, assim como iPad e iPhone.</p>

<h3>Poster:</h3>
<p>É importante adicionar o thumb enquanto o vídeo não é carregado.</p>

<h3>Controls:</h3>
<p>Caso não desenvolva os próprios controles, este atributo é necessário para que o usuário tenha o controle do vídeo.</p>

<h3>Track:</h3>
<p>Se houver a necessidade de legenda externa nos vídeos, deve-se observar que esta tag funciona apenas nos browsers abaixo a partir das versões:</p>
- Google Chome 18+<br>
- Internet Explorer 10+<br>
- Mozilla Firefox: 31+<br>
- Safari 6+<br>
- Opera 15+<br>


<h2>Browsers Suportados</h2>

<p>Todos os browsers modernos suportam o uso de HTML5:</p>
- Chrome 40+<br>
- Firefox 35+<br>
- Internet Explorer 10+ (incluindo Edge)<br>
- Opera 20+<br>
- Safari 7.0+<br>

<p>É essencial que todos anúncios funcionem nos determinados browsers e versões.</p>

<p>Este site: https://html5test.com/results/desktop.html mostra a classificação de cada browser e versão e seu desempenho.</p>
<h1>FORMATOS</h1>


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

<h1>FORMATOS</h1>


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

<p><img src="http://bn.imguol.com/1009/half-page-expansivel.jpg" style="height:228;"></p>
<dl> <dt>Exemplo</dt> <dd class="first"><a href="http://insercao.uol.com.br/galeria/galeria.php?id=2002a" target="_blank" >Veja a demonstração</a></dd> </dl>

<h1>Web Alto Impacto</h1>
<h2>Barra 1280 - Intervenção</h2>

<h3>Especificações técnicas</h3>
<dd> <strong>Tamanho Inicial:</strong> 200x446 px <br> <strong>Tamanho Expandido:</strong> min 1190x446 px - max 1190x700 px <br> <strong>Sentido de Expansão :</strong> Para Esquerda e para baixo <br> <strong>Peso HTML5:</strong> Inicial 150kb | Expandido - até 2mb <br> <strong>Backup (GIF/JPEG) :</strong> 200x446 - 40 Kb<br> <strong>Tempo de Animação :</strong> Livre <br> <strong>Looping :</strong> Livre<br> <strong>Som: </strong>Não pode ter som sem interação do usuário.<br> <strong>Vídeo: </strong>Aceita vídeos hospedados no Youtube.<br> <strong>Tag de Terceiro: </strong>Aceita<br> <br> <strong>Funcionamento:</strong> A "Barra 1280 - Intervenção" deve ser construída em 2 HTMLs, sendo um HTML com o formato retraído (200x446px) e o outro HTML com o formato expandido (min 1190x446 px max 1190x700px). </dd>

<p><img src="http://cb.i.uol.com.br/uolpublicidade/formatos/barra-1280-home.jpg" </p>
<dl> <dt>Exemplo</dt> <dd class="first"><a href="http://pubads.g.doubleclick.net/gampad/preview_cookie?gct=I2BR1rrYrCAY0IjYtgUw0KSNvgWIAYCAgKDT1_r5iQE&op=set&redirect=http://uol.com.br&redirect_hash=AJlzBa0BYy4Ct3GlVYbFHaS2TRIatSm__Q&lineItemId=278109286&creativeId=99201127246" target="_blank">Veja a demonstração</a></dd> </dl>
