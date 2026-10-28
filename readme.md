# 📚 Exemplo de Aula: Herança e Polimorfismo em Java

Este repositório contém um projeto prático desenvolvido em **Java** (utilizando Maven) para demonstrar conceitos fundamentais da **Programação Orientada a Objetos (POO)**: **Herança**, **Sobrescrita de Métodos (Override)** e **Polimorfismo**.

---

## 🎯 Objetivo do Código

O objetivo deste exemplo é simular um sistema simples de cálculo de folha de pagamento de uma empresa, onde diferentes tipos de colaboradores possuem regras distintas para o cálculo de sua remuneração final, mas são tratados de forma unificada pelo sistema.

---

## 🧠 Conceitos de POO Abordados

1. **Superclasse (Classe Base):**
   * `Funcionario`: Contém os atributos básicos comuns a todos os colaboradores (`nome` e `salarioBase`) com visibilidade `protected` (permitindo o acesso direto pelas classes filhas) e o método padrão `calcularSalario()`.

2. **Herança (`extends`):**
   * As classes `Gerente` e `Estagiario` herdam as características e comportamentos da classe `Funcionario`, reaproveitando código através da chamada ao construtor da superclasse (`super(nome, salarioBase)`).

3. **Sobrescrita de Método (`@Override`):**
   * Cada subclasse especializa o método `calcularSalario()` para incluir seus respectivos adicionais:
     * **Gerente:** Salário Base + Bônus.
     * **Estagiário:** Salário Base + Auxílio Transporte.

4. **Polimorfismo:**
   * Na classe principal (`Mavenproject2`), um único array do tipo `Funcionario[]` armazena instâncias de `Funcionario`, `Gerente` e `Estagiario`. Durante o laço de repetição (`for-each`), o Java decide em tempo de execução qual versão do método `calcularSalario()` deve ser chamada para cada objeto.

---

## 🏗️ Estrutura das Classes

| Classe | Tipo | Atributos Específicos | Regra de `calcularSalario()` |
| :--- | :--- | :--- | :--- |
| `Funcionario` | Superclasse | `nome`, `salarioBase` | Retorna apenas o `salarioBase` |
| `Gerente` | Subclasse | `bonus` | Retorna `salarioBase + bonus` |
| `Estagiario` | Subclasse | `auxilioTransporte` | Retorna `salarioBase + auxilioTransporte` |
| `Mavenproject2` | Principal (`main`) | - | Instancia a equipe, exibe os salários e soma a folha total |

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
* **Java JDK** (versão 8 ou superior) instalado.
* **Apache Maven** (opcional, caso execute via IDE como NetBeans, Eclipse ou IntelliJ).

### Passo a passo (Via Terminal)
1. Certifique-se de estar no diretório raiz do projeto ou onde o arquivo `Mavenproject2.java` se encontra.
2. Compile e execute através do Maven:
   ```bash
   mvn compile exec:java -Dexec.mainClass="br.com.aula.main.mavenproject2.Mavenproject2"
   ```

### Saída Esperada no Console
Ao executar a classe `Mavenproject2`, você verá o seguinte resultado:

```text
Paulo: R$ 3000.0
Marta: R$ 6500.0
Lucas: R$ 1400.0
Folha total: R$ 10900.0
```

---

## 💡 Exercícios Sugeridos para Aula

Para expandir este exemplo em sala de aula, tente implementar as seguintes melhorias:
1. **Encapsulamento:** Alterar os atributos de `protected` para `private` na classe `Funcionario` e criar os métodos `getters` e `setters`.
2. **Nova Subclasse:** Criar uma classe `Vendedor` que herda de `Funcionario` e possui um atributo `comissao`.
3. **Classes Abstratas:** Transformar `Funcionario` em uma classe abstrata (`abstract class`) caso não faça sentido instanciar um funcionário genérico na regra de negócio.
