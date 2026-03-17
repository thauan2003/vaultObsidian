- persistence.xml
- TipoEmpresa.java
- Empresa.java

![[image-5.png]]


1. Inserir atributo Faturamento
2. Inserir setters no Bean
3. Inserir Campos novos no xhtml
4. inserir faces-config.xml
5. Fazer a Conversão
6. Tratar nomes dos campos novos

### A Armadilha do Getter

O JSF chama os seus métodos `getListaEmpresas()` **várias vezes** em uma única requisição (durante a validação, na renderização, no processamento de eventos, etc.).

- **O Problema:** Se você colocar o acesso ao banco de dados dentro do `get`, o sistema fará, por exemplo, 5 ou 10 consultas ao banco de dados apenas para carregar uma página.
    
- **A Consequência:** Sua aplicação vai ficar pesada, o banco de dados vai fritar e você terá problemas de performance antes mesmo de o sistema entrar em produção.
    

### 2. O Papel do Metadata (`f:viewAction`)

O `<f:metadata>` com o `<f:viewAction>` serve como um **gatilho de entrada**. Ele diz ao JSF: _"Antes de começar a desenhar qualquer coisa na tela, execute este método uma única vez"_.

**O Fluxo:** 
1. O usuário acessa a URL. 
2. O JSF dispara o método no Metadata. 
3. Esse método vai ao banco, busca as empresas e as guarda na variável local do Bean. 
4. Só então a tela começa a ser desenhada, e os `getters` apenas "entregam" o que já está na memória.






3. Excluir teste
4. Preparar Bean e Página xhtml
5. Criar método no Crud Empresas
6. No Bean: Instanciar List e Crud, criar métodos de get e todas()
7. Criar dataTable com acesso ao getter, e dataView para armazenamento dos dados na memória da variável local

paginator="true" rows="10" paginatorPosition="bottom">

<f:metadata>  
    <f:viewAction action="#{gestaoEmpresasBean.todasEmpresas}"/>  
</f:metadata> <!--Acessa o metodo que popula a list de Empresas-->

<div id="conteudo">  
    <h:form>  
        <p:dataTable value="#{gestaoEmpresasBean.listaEmpresas}"  
            var="empresa" emptyMessage="Não há empresa a ser exibida!"> <!--Esse "listaEmpresa -> É o getter da List"-->  
  
           <p:column headerText="Razao Social"  sortBy="#{empresa.razaoSocial}">  
               <h:outputText value="#{empresa.razaoSocial}"/>  
           </p:column>  
  
            <p:column headerText="Nome Fantasia">  
                <h:outputText value="#{empresa.nomeFantasia}"/>  
            </p:column>  
  
            <p:column headerText="Tipo de Empresa">  
                <h:outputText value="#{empresa.tipo}"/>  
            </p:column>  
  
            <p:column headerText="Ramo Atividade">  
                <h:outputText value="#{empresa.ramoAtividade.descricao}"/>  
            </p:column>  
  
        </p:dataTable>  
    </h:form>  
</div>
<div id="conteudo">  
    <h:form>  
        <p:dataTable value="#{gestaoEmpresasBean.listaEmpresas}"  
            var="empresa" emptyMessage="Não há empresa a ser exibida!"> <!--Esse "listaEmpresa -> É o getter da List"-->  
  
           <p:column headerText="Razao Social"  sortBy="#{empresa.razaoSocial}">  
               <h:outputText value="#{empresa.razaoSocial}"/>  
           </p:column>  
  
            <p:column headerText="Nome Fantasia">  
                <h:outputText value="#{empresa.nomeFantasia}"/>  
            </p:column>  
  
            <p:column headerText="Tipo de Empresa">  
                <h:outputText value="#{empresa.tipo}"/>  
            </p:column>  
  
            <p:column headerText="Ramo Atividade">  
                <h:outputText value="#{empresa.ramoAtividade.descricao}"/>  
            </p:column>  
  
        </p:dataTable>  
    </h:form>  
</div>