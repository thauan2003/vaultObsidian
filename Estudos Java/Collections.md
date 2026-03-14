
->A Collections é uma <u>interface</u> de Java

![[image.png|438]]

---

**Tipos Principais de Collections:**

1. <span style="color:rgb(0, 176, 240)">List</span> -> Permite Objeto Repetido
```
 public static void main(String[] args) {
        List<Pessoa> pessoas = new ArrayList<>();
        //Pessoa pessoa1 = new Pessoa(1, "Jose");

        pessoas.add(new Pessoa(1,"Jose")); //Acessando o construtor diretamente do .add()
        Pessoa pessoa1 = new Pessoa(1,"Jose");
        pessoas.add(pessoa1); //Instanciando a pessoa, e inserindo dentro da list com o .add()

        for(Pessoa pessoa : pessoas){
            System.out.println(pessoa1.getNome());
        }
    }
```




2. <span style="color:rgb(0, 176, 240)">Set</span> -> Não Permite Objeto Repetido
```
public static void main(String[] args) {
        Set<Pessoa> pessoas = new HashSet<>();

        Pessoa pessoa1 = new Pessoa(1,"Jose");
        pessoas.add(pessoa1);

        for(Pessoa pessoa : pessoas){
            System.out.println(pessoa.getNome());
        }
    }
```





3. <span style="color:rgb(0, 176, 240)">Map</span>
