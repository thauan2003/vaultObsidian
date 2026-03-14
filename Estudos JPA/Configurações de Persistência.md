
## Configurações Iniciais
- Hostname: localhost 
- Port: 3306
- Username: root
- Password: 

<u>Possíveis erros ao executar algum "main" :</u>
- O Hibernate Validator utiliza o "Expression Language" para permitir que as mensagens de erro sejam dinâmicas (ex: "O campo deve ter no mínimo {min} caracteres").
	Em servidores web, o servidor fornece essa biblioteca. Em aplicações "Desktop" (método <u>main</u>), você precisa declarar essa dependência manualmente no Maven, caso contrário, o motor de validação não consegue "dar a partida".

---
## Criando o DAO

###### As classes <span style="color:rgb(0, 176, 240)">DAO</span> é onde são feitos os métodos de <span style="color:rgb(0, 176, 240)">CRUD</span> de determinada Tabela.
- C: <span style="color:rgb(0, 176, 240)">C</span>reate 
- R: <span style="color:rgb(0, 176, 240)">R</span>ead
- U: <span style="color:rgb(0, 176, 240)">U</span>pdate
- D:<span style="color:rgb(0, 176, 240)"> D</span>elete

-> **Sintaxe Básica de SQL com <span style="color:rgb(0, 176, 240)">SELECT</span>:**
" SELECT * FROM nome_tabela WHERE coluna1 = 'valor'; "

