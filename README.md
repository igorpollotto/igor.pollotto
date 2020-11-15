alteração
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Resolução Prova</title>
	<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.1/css/all.css">

	<style>
		.tableJogoVelha{
			margin: auto;
		}

		.celula{
			width: 30px;
    		height: 30px;
		}
		.tabela{
			display: flex;
			text-align: center;
		}
	</style>
</head>
<body>
		<h1 align="center">Jogo da Velha</h1>
		<div id="mostrador">
		<p align="center" onclick="">Vez do jogador: </p>
		<img align="center" src="imagens/x.png" dorder="0" height="50">
		</div>
		<div align="center" id="Game">
		<table class="tableJogoVelha"  border="1">
			<tr>
				<td class="celula" id="linha1Coluna1" onclick="adcXaqui('linha1Coluna1',1)">	
				</td>
				<td class="celula" id="linha1Coluna2" onclick="adcXaqui('linha1Coluna2',2)">		
				</td>
				<td class="celula" id="linha1Coluna3" onclick="adcXaqui('linha1Coluna3',3)">
				</td>
			</tr>
			<tr>
				<td class="celula" id="linha2Coluna1" onclick="adcXaqui('linha2Coluna1',4)">
				</td>
				<td class="celula" id="linha2Coluna2" onclick="adcXaqui('linha2Coluna2',5)">
				</td>
				<td class="celula" id="linha2Coluna3" onclick="adcXaqui('linha2Coluna3',6)">
				</td>
			</tr>

			<tr>
				<td class="celula" id="linha3Coluna1" onclick="adcXaqui('linha3Coluna1',7)">
				</td>
				<td class="celula" id="linha3Coluna2" onclick="adcXaqui('linha3Coluna2',8)">
				</td>
				<td class="celula" id="linha3Coluna3" onclick="adcXaqui('linha3Coluna3',9)">
				</td>
			</tr>
		</table>
	</div>
</body>
	<script type="text/javascript">
		var quadrantesMarcados = []; //sempre quando aperta em 1 quadrante ele adiciona em uma array
		var arrayIdComQuadrante = [
		"", //index 0
		"linha1Coluna1", //index 1
		"linha1Coluna2", //index 2
		"linha1Coluna3", //index 3
		"linha2Coluna1", //index 4
		"linha2Coluna2", //index 5
		"linha2Coluna3", //index 6
		"linha3Coluna1", //index 7
		"linha3Coluna2", //index 8
		"linha3Coluna3", //index 9
		]
		function adcXaqui(idCelula, quadrante){
			if (quadrantesMarcados.indexOf(quadrante) == -1 ) {
				preencherVelha(idCelula, 'x', quadrante)
			efetuarJogadaDaMaquina()
			}
		}
		function efetuarJogadaDaMaquina(){
			var quadranteMaquina = Math.floor(Math.random() * 10);
			if(quadrantesMarcados.indexOf(quadranteMaquina) == -1 ){
				console.log("nao achei quadrante" + quadranteMaquina);
				
				idQuadranteEscolhidoPelaMaquina = arrayIdComQuadrante[quadranteMaquina]
	
				preencherVelha(idQuadranteEscolhidoPelaMaquina, '0', quadranteMaquina)
			}else{
				console.log("achei preenchido" + quadranteMaquina);
			}
		}
		function preencherVelha(idQuadrante, tipo, valorQuadrante){
			if (valorQuadrante == 0) {
				return;
			}

			var elemento = document.getElementById(idQuadrante);
			if (tipo == 'x') {
				elemento.innerHTML = "<i class='fas fa-times'></i>";
			}else{
				elemento.innerHTML = "<i class='far fa-circle'></i>";
			}
			quadrantesMarcados.push(valorQuadrante);
			
		}
		const player1 = "X";
		const player2 = "O";
		var playTime = player1;
		var gameOver = false;

		atualizarMostrador();

		function atualizaMostrador(){
			if(gameOver) {return;}

			if(playTime == player1){
				var player = document.querySelectorAll("div#mostrador img")[0];
				player.setAttribute("src", "imagens/x.png");
			}else{
				var player = document.querySelectorAll("div#mostrador img")[0];
				player.setAttribute("src", "imagens/o.png");
			}
		}

	</script>
</html>
