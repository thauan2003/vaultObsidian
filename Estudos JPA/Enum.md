O Enum seria como uma classe Java convencional, porém é usado apenas para definir **constantes**.

**Ex**: 
```
public enum EnumTeste {

    VAL1("Valor Grande 1"),
    VAL2("Valor Grande 1");

    private String descricao;

    //Construtor do Enum
    EnumTeste(String descricao) {
        this.descricao = descricao;
    }

    public String getDescricao() {
        return descricao;
    }

}
```

- E para instanciar num, e obter o valor de alguma das constantes num código ficaria: 
```
EnumTeste enum1 = EnumTeste.VAL1;

EnumTeste.VAL1.getDescricao()
```