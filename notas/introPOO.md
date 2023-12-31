# Introducao a POO

-[x] quero modelar um aluno
-[x] quero modelar 100 alunos

```java
int quantidade = 100;
String[] matriculas = new String[quantidade];
String[] nomes = new String[quantidade];
double[] notas = new double[quantidade];
int[] idades = new int[quantidade];
```

## Trocar duas variaveis

```java
int a = 2, b = 3;
int aux = a;
a = b;
b = aux;
```

## Problemas da nao POO

- O codigo não é legível dentro do produto desejado.
- Dificuldade de manipular e gerenciar muitos dados.
- Complexidade desnecessaria em coisas simples: ordenar, trocar, etc.

## POO

- Classe: molde ou classificacao
- Objeto: fruto do molde ou instancia (caso particular)

```java
class Aluno {
  // tem - atributos
  String matricula;
  String nome;
  int idade;
  double nota;

  // faz - metodo
  int somar(int a, int b) {
    return a + b;
  }

  void dizerOi(String nome) {
    System.out.println("Oi, " + nome);
  }
}
```

```java
class Application {
  public static void main(String[] args) {
    Aluno joao = new Aluno();
    joao.matricula = "1234A";
    joao.nome = "Joao da Silva";

    Aluno[] turma = new Aluno[100];

    Aluno aux = turma[0];
    turma[0] = turma[5];
    turma[5] = aux;
  }
}
```

## Construtores

- Metodo construtor

```java
class Aluno {
  // tem - atributos
  String matricula;
  String nome;
  int idade;
  double nota;

  // construtor padrao (omitido por padrao)
  Aluno() {
  }

  // faz - metodo
  int somar(int a, int b) {
    return a + b;
  }

  void dizerOi(String nome) {
    System.out.println("Oi, " + nome);
  }
}
```

## Sobrecarga (overload)

```java
int soma(int a, int b) {
  return a + b; 
}

int soma(int a, int b, int b) {
  return a + b + c;
}
```

```java
public class Aluno {
  // tem - atributos
  public String matricula;
  public String nome;
  public int idade;
  public double nota;

  public Aluno() {
  }

  public Aluno(String matricula, String nome) {
    this.matricula = matricula;
    this.nome = nome;
  }

  public Aluno(String matricula, String nome, int idade) {
    this.matricula = matricula;
    this.nome = nome;

    if(idade < 18) 
      return;

    this.idade = idade;
  }

}
```

## Encapsulamento

- o que é? esconder e proteger a lógica da classe dentro da classe
- getters and setters
