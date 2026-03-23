Passos:
1. Importe
	no Layout:
		xmlns:p="http://primefaces.org/ui"  
		xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
	no Template:
		xmlns:p="http://primefaces.org/ui"  
		xmlns:ui="http://xmlns.jcp.org/jsf/facelets"  
		template="WEB-INF/template/Layout.xhtml"  
		lang="pt-BR">

2. No layout, trocar conteudos e titulos por <ui:insert...>
3. Na Pagina: 
	Metadata fica no body
	Altera body e head para <ui:define>, e html para <ui:composition>
	Remove Footer e Header, e DOCTYPE