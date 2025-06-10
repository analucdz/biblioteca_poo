<body>
    <center>
  <h1 align="center"> Sistema de Gerenciamento de Biblioteca </h1>
      <hr>
  <br>
      <div align="center">
        </div>

<div align="center">
        <ul>
          <li align="left"; ><b> Imagine uma biblioteca onde os livros não fogem das prateleiras, os empréstimos não viram um drama e o silêncio é quebrado apenas pelo clique satisfeito de um sistema superinteligente! <br></li>
          <li align="left"; ><b>Com o nosso sistema de gerenciamento, coordenar acervos, usuários e empréstimos vira um passeio no parque — ou melhor, um passeio entre as estantes. <br></li>
          <li align="left"; ><b> De clássicos empoeirados a best-sellers disputados, nosso sistema organiza, controla e até manda lembretes carinhosos (ou insistentes) para aquela pessoa que sempre atrasa a devolução. Porque, no fim, toda biblioteca merece um final feliz… e sem multas! 📚✨  <br></li>
        </ul>
            <hr>
            <hr>


</div> 
<br>

<p align="left"> <br>
<b> O que você poderá fazer com nosso sistema: </b> <br> <br> 
    - ✅ Adicionar novo livro <br> <br> 
    - 🔍 Pesquisar livro por título <br> <br> 
    - 🗑️ Excluir livro por título <br> <br> 
    - 📜 Listar todos os livros <br> <br> 
</p> 


<br>
  <hr>
<br>


# ☕ Primeiro - A ideia geral:
- Esse programa é como um "sistema de bibliotecário virtual", utilizando o ArrayList como base. Ele te deixa cadastrar livros, procurar livros pelo título, remover livros, e ver tudo o que já foi cadastrado. Tudo isso usando um menu simples no terminal.

<br>
<br>


# 🛠️ Estrutura do Código
- Variáveis principais:
- Dois ArrayLists que trabalham juntos para manter seu acervo organizado (sim, é uma gambiarra, mas funciona...o que é uma beleza, né?)
```java
ArrayList<String> titulos = new ArrayList<>();  // Armazena títulos dos livros
ArrayList<String> autores = new ArrayList<>();  // Armazena autores correspondentes
Scanner scanner = new Scanner(System.in);       // Para entrada de dados
```

<br>
<br>

# 🖥️ Método exibirMenu()
- Mostra o cardápio de opções pro usuário. É só aquele bloquinho que imprime:
```java
private static void exibirMenu() {
    System.out.println("\n===== 📚 MENU PRINCIPAL 📚 =====");
    System.out.println("1. ➕ Adicionar novo livro");
    System.out.println("2. 🔍 Pesquisar livro");
    System.out.println("3. 🗑️ Remover livro");
    System.out.println("4. 📜 Listar todos");
    System.out.println("5. 🚪 Sair");
    System.out.print("👉 O que você quer fazer? ");
}
```


<br>
<br>

# 🔄 Loop Principal / Opções 
- Mantém o programa em execução até o usuário escolher sair.
```java
        Menu.exibir();

 switch (opcao) {
                    case 1 -> Adicionar.executar(scanner);
                    case 2 -> Pesquisar.executar(scanner);
                    case 3 -> Remover.executar(scanner);
                    case 4 -> Listar.executar();
                    case 5 -> Encerrar.executar();
                    default -> System.out.println("\n🤨 Opção inválida, meu chapa! Tenta de 1 a 5, por favor.");
                }
```

    
<br>
<br>

# ➕ Adicionar Livro 
- Converte tudo para MAIÚSCULAS para padronizar.
- Valida se os campos não estão vazios.
- Mostra feedback animado após adicionar.
```java
public class Adicionar {
    public static void executar(Scanner scanner) {
        System.out.print("\n📝 Qual o título do livro? ");
        String titulo = scanner.nextLine().toUpperCase();

        System.out.print("📝 E quem é o autor? ");
        String autor = scanner.nextLine().toUpperCase();

        BibliotecaDados.adicionarLivro(titulo, autor);
        System.out.println("\n✅ Boa! Livro adicionado com sucesso!");
    }
}
```


<br>
<br>

# 🔍 Pesquisar Livro
- Busca por correspondência parcial (não precisa digitar o nome completo).
- Mostra a posição do livro na estante.
- Feedback visual quando encontra ou não o livro.
```java
public class Pesquisar {
    public static void executar(Scanner scanner) {
        System.out.print("\n🔍 Qual livro tá procurando? (pode ser só parte do nome) ");
        String busca = scanner.nextLine().toLowerCase();
        boolean encontrou = false;
        System.out.println("\n🕵️‍♂️ Resultados da sua pesquisa:");
        for (int i = 0; i < BibliotecaDados.titulos.size(); i++) {
            if (BibliotecaDados.titulos.get(i).toLowerCase().contains(busca)) {
                System.out.println("📖 Título: " + BibliotecaDados.titulos.get(i));
                System.out.println("✍️ Autor: " + BibliotecaDados.autores.get(i));
                System.out.println("-----------------------------");
                encontrou = true;
            }
        }
        if (!encontrou) {
            System.out.println("😵‍💫 Nada encontrado com '" + busca + "'. Tem certeza que escreveu certo?");
        }
    }
}
```

<br>
<br>

# ❌ Remover Livro
- Remove pelo título exato (case sensitive).
- Atualiza o contador de livros automaticamente.
```java
public class Remover {
    public static void executar(Scanner scanner) {
        System.out.print("\n🗑️ Qual livro quer remover? (digite o título exato) ");
        String tituloRemover = scanner.nextLine().toUpperCase();
        int index = BibliotecaDados.titulos.indexOf(tituloRemover);
        if (index != -1) {
            BibliotecaDados.titulos.remove(index);
            BibliotecaDados.autores.remove(index);
            System.out.println("\n🗑️ Pronto! Livro apagado da existência!");
        } else {
            System.out.println("\n🤷‍♂️ Ixi, não achei esse livro aí...");
        }
    }
}
```

<br>
<br>

# 📚 Listar todos os Livros
-Mostra todos os livros numerados.
- Formatação bonitinha com separadores.
- Mensagem especial quando a biblioteca está vazia.
```java
public class Listar {
    public static void executar() {
        if (BibliotecaDados.titulos.isEmpty()) {
            System.out.println("\n📚 Taí uma biblioteca triste... Nenhum livro ainda!");
        } else {
            System.out.println("\n📚 Acervo completo (" + BibliotecaDados.titulos.size() + " livros):");
            for (int i = 0; i < BibliotecaDados.titulos.size(); i++) {
                System.out.println("📖 Título: " + BibliotecaDados.titulos.get(i));
                System.out.println("✍️ Autor: " + BibliotecaDados.autores.get(i));
                System.out.println("-----------------------------");
            }
        }
    }
}
```

<br>
<br>

# 🛠️ Tecnologias Utilizadas
- ArrayList para armazenamento dinâmico.
- Scanner para entrada de dados.
- Muitos emojis para melhorar a experiência do usuário.

<br>
     <hr>
     <hr>


  ![eecf0ac7-3f37-4b8c-9d1b-a30660504d9d](https://github.com/user-attachments/assets/dffb81c8-3915-40fe-b279-784943908139)

</div>
