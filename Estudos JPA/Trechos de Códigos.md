
<!DOCTYPE html>  
<html xmlns="http://www.w3.org/1999/xhtml"  
      xmlns:h="http://java.sun.com/jsf/html"  
      xmlns:f="http://java.sun.com/jsf/core"  
      xmlns:p="http://primefaces.org/ui"  
      lang="pt-BR">  
<h:head>  
  
    <meta charset="UTF-8"/>  
    <title>Gestao de Empresa</title>  
  
    <h:outputStylesheet library="algaworks" name="estilo.css"/> <!--Importo minha library de estilo p/ o sist.-->  
  
</h:head>  
  
<body>  
  
<header>  
    <h:graphicImage library="algaworks" name="logo.png"/>  
</header>  
  
<div id="conteudo">  
    <h:form>  
        <h:panelGrid columns="2">  
  
                <p:outputLabel value="Razao Social*:  " for="razaoSocial"/>  
            <h:panelGroup>  
                <p:inputText id="razaoSocial" value="#{gestaoEmpresasBean.empresa.razaoSocial}"  
                             required="true"/>  
  
                    <p:message for="razaoSocial"/>  
            </h:panelGroup>  
  
            <p:outputLabel value="Nome Fantasia:  " for="nomeFantasia"/>  
            <p:inputText id="nomeFantasia" value="#{gestaoEmpresasBean.empresa.nomeFantasia}"/>  
  
                <p:outputLabel value="Tipo de Empresa*:  " for="tipo"/>  
                <h:panelGroup> <!--Guarda 1 valor no tipo de Empresa-->  
                    <p:selectOneMenu id="tipo" value="#{gestaoEmpresasBean.empresa.tipo}"  
                     required="true">  
                        <f:selectItem itemLabel="Selecione..."/>  
                        <f:selectItems value="#{gestaoEmpresasBean.tipoEmpresa}"  
                            var="tipoEmpresa" itemLabel="#{tipoEmpresa.descricao}"  
                            itemText="#{tipoEmpresa}" /> <!--Acessa um array com os tipos de Empresa para exibir-->  
                    </p:selectOneMenu>  
  
                    <p:message for="tipo"/>  
            </h:panelGroup>  
  
            <p:outputLabel value="Data de Fundacao:  " for="data"/>  
            <h:panelGroup>  
            <p:inputText id="data" value="#{gestaoEmpresasBean.empresa.dataFundacao}">  
                <f:convertDateTime pattern = "dd/MM/YYYY"/>  
            </p:inputText>  
  
                <p:message for="data"/>  
  
            </h:panelGroup>  
  
            <p:outputLabel value="Faturamento:  " for="faturamento"/>  
            <h:panelGroup>  
                <p:inputText id="faturamento" value="#{gestaoEmpresasBean.empresa.faturamento}">  
                    <f:convertNumber pattern="#,##0.000"/>  
                </p:inputText>  
  
                <p:message for="faturamento"/>  
            </h:panelGroup>  
  
            <h:outputLabel />  
            <p:commandButton value="Salvar" actionListener="#{gestaoEmpresasBean.salvar}"  
            update="@form"/>  
  
            <h:outputLabel />  
            <p:commandLink value="Ajuda" action="#{gestaoEmpresasBean.ajuda}"/>  
  
        </h:panelGrid>  
  
  
  
        <p:dataTable value="#{[0, 0, 0, 0]}">  
  
            <p:column headerText="Razao Social">  
                <h:outputText value="1ª Razao Social"/>  
            </p:column>  
  
            <p:column headerText="Nome Fantasia">  
                <h:outputText value="1ª Nome Fantasia"/>  
            </p:column>  
  
            <p:column headerText="Tipo de Empresa">  
                <h:outputLabel value="Tipos de Empresas"/>  
            </p:column>  
        </p:dataTable>  
  
    </h:form>  
</div>  
  
<footer>  
    Curso Algaworks em processo!  
</footer>  
</body>  
  
</html>