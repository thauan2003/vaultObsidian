<u>Configurando o CDI:</u>

1. pom.xml
```
<dependency>  
    <groupId>org.jboss.weld.servlet</groupId>  
    <artifactId>weld-servlet</artifactId>  
    <version>2.4.0.Final</version>  
    <scope>compile</scope>  
</dependency>
```

2. webapp > META-INF > context.xml
```
<?xml version="1.0" encoding="UTF-8"?>  
<Context>  
    <Manager pathname="" />  
  
    <Resource auth="Container" name="BeanManager" type="javax.enterprise.inject.spi.BeanManager"  
    factory="org.jboss.weld.resources.ManagerObjectFactory" />  
</Context>
```

3. webapp > WEB-INF > web.xml
```
<resource-env-ref>  
    <resource-env-ref-name>BeanManager</resource-env-ref-name>  
    <resource-env-ref-type>javax.enterprise.inject.spi.BeanManager</resource-env-ref-type>  
</resource-env-ref>  
  
<listener>  
    <listener-class>org.jboss.weld.environment.servlet.Listener</listener-class>  
</listener>
```

### ### 1. O que é o CDI na prática?

Imagine que você tem uma aula `CalculadoraArea`. No modo "Common Learner", você faria: `CalculadoraArea calc = new CalculadoraArea();`

No modo CDI, você apenas diz: `@Inject CalculadoraArea calc;`

O CDI servirá para **instanciar** e **gerenciar**(inclusive com <u>Interceptor</u>) essa memória para você. Isso é o que chamamos de Inversão de Controle .

---

### 2. Os "Escopos" (Quanto tempo o objeto vive?)

O CDI usa anotações para saber quando criar e destruir um objeto:

- **@RequestScoped:** O objeto nasce quando alguém acessa uma página e morre quando uma resposta é enviada( = requisição get no ManagedBean). (Ótimo para aulas utilitárias de processamento rápido).
    
- **@SessionScoped:** O objeto vive enquanto o usuário está logado ou com o navegador aberto, ou seja caso seja reaberto o navegador gera-se uma nova instância. (Ideal para Carrinhos de Compra ou Perfil de Usuário).
    
- **@ApplicationScoped:** O objeto é uma correção de "alto desempenho". Ele nasce quando o servidor liga e só morre quando desliga, ou seja, dura enquanto a aplicação Tomcat estiver rodando.
    
- **@ViewScoped:** Se trata de um objeto que nasce quando a tela é acessa, morre quando é acessada novamente, pois se gera uma nova instância, ou quando há uma navegação ( = requisição get no ManagedBean) -> O mais utilizado
	Ou seja, com a inserção de um componte de JSF que possua um outcome, seja navegação Implícita ou Explícita!
---

### 3. A anotação @Named

Para que seu **JSF/PrimeFaces** consiga "enxergar" uma classe Java, o CDI usa o `@Named`. Sem isso, o código Java e a página `.xhtml`não se conversam.

## Classe
1. EntityManagerProducer
	Método que fornece a instância do EM

2. EntityManagerInterceptor
[[LifecycleInterceptor.canvas]]
*"@Transacional" -> Essa anotação diz ao CDI que é para os métodos dessa classe serem interceptados, pode colocar a anotação apenas nos métodos que deseja serem interceptados
