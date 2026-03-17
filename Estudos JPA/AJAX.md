### Realiza uma atualização Parcial do código ao realizar uma requisição desse tipo!

 - <u>Atributos Comuns:</u>
	1. update
	2. process
	3. async
	4. onstart
	5. onerror
	6. onsuccess

-> Ou seja, componentes que geram requisições, como "commandButton"/"CommandLink", agora precisam possui o atributo "update" que aponte ao "id" do que será atualizado!
*Porém se um commandButton ja possuir um update que atualize determinado bloco de componentes, os outros não necessitarão possuir o update* : Exemplo um botão de <u>Salvar</u>


| Update Ajax                                                                                                                                   | Update Java                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Insere os novos dados, e ao pressionar um botão de action, através do JS, atualiza de forma assíncrona e parcial os valores mostrados em tela | Insere os dados novos no BD, porém não atualiza os valores mostrado em tela |

