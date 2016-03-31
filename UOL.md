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
<a href="" id="clickArea" target="_blank"></a>
<script type="text/javascript">
    var clickTag = "%%CLICK_URL_ESC%%%%DEST_URL%%";
    document.getElementById('clickArea').href = clickTag;   
</script>
</code>
</pre>pre>
<p>Obs. Lembrando que a 'clickArea' precisa existir em seu HTML e seja a área clicável para redirecionamento. Além disso a chamada javascript deve vir após a existência do elemento clickArea no HTML. </p>

<h2>HTML</h2>
<p>Outra possibilidade é feito no próprio elemento HTML, conforme exemplos abaixo:</p>
<h2>Ex 1 HTML puro:</h2>
<code><a href="%%CLICK_URL_ESC%%%%DEST_URL%%" target="_blank" ></a></code>

<h2>Ex 2 HTML + Javascript:</h2>
<code>  
var clickTag = '%%CLICK_URL_ESC%%%%DEST_URL%%';
<a href="javascript: window.open(clickTag, '_blank'); void(0)"></a></code>

<h2>Ex 3 HTML + Javascript em um elemento DIV:</h2>
<code><div id="clickArea" onclick="javascript: window.open(clickTag, '_blank'); void(0)" style="cursor:pointer;" ></div</code>
<p>Obs. No uso de DIV clicável, ela deve sempre exibir o cursor de 'mão'.</p>

<h2>Múltiplos Cliques</h2>
<p>Em casos de várias urls de clique dentro do mesmo anúncio, declare as variáveis de click da seguinte forma: clickTag, clickTag1, clickTag2, caso deseje utilizar via javascript.</p>
<code>var clickTag = "%%CLICK_URL_ESC%%http://www.uol.com.br"; <br>
var clickTag1 = "%%CLICK_URL_ESC%%http://economia.uol.com.br";<br>
var clickTag2 = "%%CLICK_URL_ESC%%http://esporte.uol.com.br";<br>
var clickTag3 = "%%CLICK_URL_ESC%%http://entretenimento.uol.com.br";</code>
