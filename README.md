# kotlin-00-classes-e-construtores

Vamos analisar os códigos apresentados e entender as diferenças entre Kotlin e Java, bem como os conceitos de **classes, construtores e interoperabilidade**. Vou explicar as vantagens do Kotlin e demonstrar como implementar tudo apenas em Kotlin.

---

### **O que o código está ensinando**
Esse código ensina os conceitos básicos de **classes e construtores** em Kotlin e Java:

1. **Classes em Kotlin**:
   - Kotlin tem uma sintaxe mais concisa para declarar classes e seus construtores.
   - Propriedades (`val` e `var`) podem ser declaradas diretamente no construtor primário.

2. **Construtores em Java**:
   - Em Java, os construtores precisam ser declarados explicitamente e costumam ser mais verbosos.

3. **Interoperabilidade**:
   - O código mostra como Kotlin e Java podem coexistir. Por exemplo, a classe `JavaEmployee` pode ser usada em projetos Kotlin sem modificações.

---

### **Análise do código Kotlin**

#### **Kotlin: Classes e Construtores**

```kotlin
class Employee(val firstName: String, var fullTime: Boolean = true)
```

1. **Construtor primário**:
   - Declarado diretamente na linha da classe.
   - Propriedade `firstName` é `val` (imutável).
   - Propriedade `fullTime` é `var` (mutável) com valor padrão `true`.

2. **Uso da classe**:
   ```kotlin
   val emp = Employee("John")
   println(emp.firstName)  // Output: John
   println(emp.fullTime)   // Output: true
   ```

#### **Kotlin: Construtores Secundários**

```kotlin
class Demo {
    val dummy: String

    constructor() {
        dummy = "Hello"
    }
}
```

- Um construtor secundário é explicitamente declarado usando `constructor`.
- Útil quando há lógica adicional ao inicializar objetos.

---

### **Análise do código Java**

```java
public class JavaEmployee {

    private final String firstName;
    private final boolean fullTime;

    public JavaEmployee(String firstName) {
        this.firstName = firstName;
        this.fullTime = true;
    }

    public JavaEmployee(String firstName, boolean fullTime) {
        this.firstName = firstName;
        this.fullTime = fullTime;
    }
}
```

1. **Construtores separados para lógica diferente**:
   - Um construtor assume `fullTime = true` como padrão.
   - Outro aceita um valor específico para `fullTime`.

2. **Verboso**:
   - É necessário declarar explicitamente as variáveis de instância e inicializá-las nos construtores.

---

### **Vantagens do Kotlin sobre Java**
1. **Menos código repetitivo**:
   - Em Kotlin, o construtor primário já declara as propriedades da classe.
   - Não há necessidade de inicializar variáveis em construtores separados.

2. **Valores padrão**:
   - Kotlin permite valores padrão diretamente no construtor (`fullTime: Boolean = true`).

3. **Imutabilidade explícita**:
   - Propriedades podem ser declaradas como `val` (imutáveis), algo que não é tão direto em Java.

4. **Concisão**:
   - A declaração de classes e construtores em Kotlin é mais curta e legível.

---

### **Como ficaria tudo apenas em Kotlin**

Aqui está a versão 100% Kotlin, sem necessidade de Java:

```kotlin
package academy.learnprogramming.accessmodifiers

fun main(args: Array<String>) {
    val emp = Employee("John")
    println(emp.firstName)  // John
    println(emp.fullTime)   // true

    val emp2 = Employee("Jane", false)
    println(emp2.firstName) // Jane
    println(emp2.fullTime)  // false

    val demo = Demo()
    println(demo.dummy)     // Hello
}

// Classe Employee
class Employee(val firstName: String, var fullTime: Boolean = true)

// Classe Demo com construtor secundário
class Demo {
    val dummy: String = "Hello"
}
```

- **Propriedades padrão**: `fullTime` é inicializada como `true` no construtor.
- **Construtores compactos**: A classe `Demo` usa inicialização direta para `dummy`, eliminando a necessidade de um construtor explícito.

---

### **Conclusão**
#### Por que esse código é ensinado: 
````
package academy.learnprogramming.javacode;

public class JavaEmployee {

    private final String firstName;
    private final boolean fullTime;

    public JavaEmployee(String firstName) {
        this.firstName = firstName;
        this.fullTime = true;
    }

    public JavaEmployee(String firstName, boolean fullTime) {
        this.firstName = firstName;
        this.fullTime = fullTime;
    }

}

````
1. Para mostrar como Kotlin reduz a verbosidade em relação ao Java.
2. Para ensinar construtores primários e secundários.
3. Para demonstrar a interoperabilidade entre Kotlin e Java, uma característica importante para projetos que migram de Java para Kotlin.

#### Vantagem de usar apenas Kotlin:
1. Menos código.
2. Mais legibilidade.
3. Foco nas funcionalidades modernas sem carregar a verbosidade do Java.

Se você deseja aprender Kotlin como substituto do Java, é útil evitar padrões Java-like e adotar práticas idiomáticas Kotlin, como valores padrão e inicialização direta. 🚀

Interoperabilidade Kotlin-Java
A interoperabilidade entre Kotlin e Java é um benefício real e prático, mas neste exemplo específico, ela não está sendo explorada. Isso porque:

Você comentou o código Java e o Kotlin continuou funcionando perfeitamente.
A funcionalidade implementada no Kotlin é independente do código Java.
A interoperabilidade seria usada se, por exemplo, o código Kotlin chamasse diretamente o construtor de JavaEmployee ou utilizasse métodos dessa classe Java. Algo assim:

* kotlin
````
fun main() {
    val javaEmp = JavaEmployee("John")
    println(javaEmp.firstName) // Aqui seria interoperabilidade real
}
````
Mas no caso, o exemplo é autossuficiente em Kotlin, então o código Java está ali apenas como referência didática.
