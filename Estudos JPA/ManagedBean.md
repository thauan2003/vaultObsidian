### O ManagedBean (ou Backing Bean) é o grande "maestro" da sua aplicação JSF. Ele é o componente que faz a ponte entre a sua página web (.xhtml) e a lógica de negócio no Java.

Se usarmos a analogia do restaurante que vimos antes, o ManagedBean é o garçom: ele recebe o seu pedido (dados da tela), leva para o cozinheiro (Camada de Modelo/Banco de Dados) e traz o prato pronto de volta para a sua mesa (atualiza a tela).

Aqui está o papel dele dividido em três funções principais:

1. Guardar o Estado da Tela (Data Binding)
O ManagedBean possui atributos (variáveis com getters e setters) que estão vinculados aos campos da sua tela.

Se você digita o nome de uma empresa em um <p:inputText>, o ManagedBean guarda esse valor em uma variável String nome.

Se você seleciona um item em um Combo (p:selectOneMenu), o ManagedBean guarda o objeto selecionado.

2. Tratar os Eventos (Ações do Usuário)
Quando o usuário clica em um botão (<p:commandButton>), o JSF chama um método dentro do seu ManagedBean.

<u>Exemplo</u>: O botão "Salvar" invoca o método public void salvar().
Dentro desse método, o Bean decide o que fazer: validar os dados, chamar o EntityManager ou disparar uma mensagem de erro na tela.

3. Controlar a Navegação e o Fluxo
O ManagedBean decide o que o usuário verá em seguida.
Após salvar um contato, o Bean pode retornar uma String com o nome de outra página (ex: "ListagemContatos?faces-redirect=true") para redirecionar o usuário.

*O papel dele é apenas coordenação. * Ele recebe os dados da View e os repassa para uma classe de Service ou Repository

**Resumo do Fluxo:**
1. View (.xhtml): O usuário preenche o formulário.
2. ManagedBean: Captura os dados via Setters.
3. ManagedBean: O usuário clica em "Salvar", o Bean chama o método de ação.
4. Model (Service/Repository): O Bean envia os dados para serem processados/salvos.
5. View (.xhtml): O Bean devolve uma mensagem de sucesso ou atualiza uma tabela via Getters.
