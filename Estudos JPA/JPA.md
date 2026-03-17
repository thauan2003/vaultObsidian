[[Anotações]]
[[MVCImg]]
*Conceito: Conjunto de Especificações de Persistência em Java*

**Áreas Padronizadas**

- API Operações
	Operações padronizadas -> CRUD

- JPQL (Java Persistence Query Language)
	Códigos de CRUD que são traduzidos para a linguagem nativa do SQL usado. 
	O Banco de Dados é abstraido.
	É parecido com SQL comum

- Criteria
	Faz consultas ao BD com código java

- Metadados
	Anotações que dizem que uma classe aponta para determinada tabela, e uma propriedade está apontando para uma determinada coluna no BD

*Nesse caso o Hibernate seria uma: Implementação*

->O <span style="color:rgb(0, 176, 240)">context</span> seria uma tag que engloba o código do "<span style="color:rgb(0, 176, 240)">Manager</span>":
```
<Context>
   Código
</Context> 
```

## CDI
É um framework para injeção de dependências no Java