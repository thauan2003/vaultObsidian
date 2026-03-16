-> Toda requisição "http" que chega na minha aplicação, vem como <u>String</u>
Por isso é necessário realizar a Conversão e Validação para tipos específicos, como: Date, Currency, etc...

*Componentes de Conversão comuns:* 
- <h:convertDateTime/>
- <h:convertNumber/>

*Componentes de Validação comuns: *
 - Atributo required="true" -> Torna o preenchimento do campo obrigatótio
 - <f:validateLength minimum="" maximum="" />  --> Valida quantidade de numeros
 - <f:validateDoubleRange minimum="" maximum="" />  --> Validade valor mínimo/máximo
 - ,etc...