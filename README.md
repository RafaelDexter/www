# www
https://phcode.dev/
```
<!DOCTYPE html>
<html>
<head>
  <title>Equação do Segundo Grau</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Equação do Segundo Grau</h1>
	<h2>ax<sup>2</sup>+bx+c=0</h2>
  <form id="equation-form">
    <input type="number" id="valor-a" required class="var col-1" size="3" maxlength="3" placeholder="a">
		<var>x<sup>2</sup> +</var>
    <input type="number" id="valor-b" required class="var col-1" size="3" maxlength="3" placeholder="b">
		<var>x +</var>
    <input type="number" id="valor-c" required class="var col-1" size="3" maxlength="3" placeholder="c">
    <var>= 0</var>
		<br>
    <button type="submit">Calcular</button>
  </form>
  <div id="result"></div>
  <script src="script.js"></script>
</body>
</html>
```

```
// Referências aos elementos HTML
const equationForm = document.getElementById('equation-form');
const resultDiv = document.getElementById('result');

// Função para calcular as raízes usando a fórmula de Bhaskara
function Bhaskara(a, b, c) {
  const delta = b * b - 4 * a * c;
  let raizes;

  if (delta > 0) {
    const root1 = (-b + Math.sqrt(delta)) / (2 * a);
    const root2 = (-b - Math.sqrt(delta)) / (2 * a);
    raizes = `As raízes são ${root1.toFixed(2)} e ${root2.toFixed(2)}`;
  } else if (delta === 0) {
    const root = -b / (2 * a);
    raizes = `A raiz é ${root.toFixed(2)}`;
  } else {
    raizes = 'Não existem raízes reais';
  }

  return raizes;
}

// Manipulador de evento para o envio do formulário
equationForm.addEventListener('submit', function(event) {
  event.preventDefault();

  // Obter valores de a, b e c
  const a = parseFloat(document.getElementById('valor-a').value);
  const b = parseFloat(document.getElementById('valor-b').value);
  const c = parseFloat(document.getElementById('valor-c').value);

  // Calcular as raízes
  const raizes = Bhaskara(a, b, c);

  // Exibir o resultado
 
  resultDiv.textContent = raizes;
  alert(raizes)
});
```

```
.var{
    display:inline-block;
    font-weight:400;
    text-align:center;
    white-space:nowrap;
    vertical-align:middle;
    -webkit-user-select:none;
    -moz-user-select:none;
    -ms-user-select:none;
    user-select:none;
    border:1px solid transparent;
		padding: 1rem 0 1rem 0; 
    font-size:1rem;
    line-height:1.25;
    border-radius:.25rem;
    transition:all .15s ease-in-out;
		margin: none;
}

.lo-caol{
    width:100%;
    min-height:1px;
    padding-right:15px;
    padding-left:15px
}
.col-1{
    position:relative;
    -ms-flex:0 0 8.333333%;
    flex:0 0 8.333333%;
    max-width:3rem
}
```
