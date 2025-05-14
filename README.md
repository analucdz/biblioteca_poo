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
        <img src="https://github.com/user-attachments/assets/7aa9b3f5-a1b2-49af-b588-364a9c8f18a4" width="300px" style="border-radius: 90px"; align="right">

</div> 
<br>

<p align="left"> <br>
<b> O que você poderá fazer com nosso sistema: </b> <br> <br> 
    - ✅ Adicionar novo livro (porque toda biblioteca precisa de mais aventuras!) <br> <br> 
    - 🔍 Pesquisar livro por título (para achar aquele romance perdido no meio dos clássicos) <br> <br> 
    - 🗑️ Excluir livro por título (se ele for muito antigo, muito danificado ou muito chato) <br> <br> 
    - 📜 Listar todos os livros (e se perder na sua própria coleção como se fosse um leitor apaixonado) <br> <br> 
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

# 🔄 Loop Principal
- Mantém o programa em execução até o usuário escolher sair.
```java
do {
    exibirMenu();
    // ... tratamento de entrada
    switch (opcao) {
        // ... casos do switch
    }
} while (opcao != 5);
```

    
<br>
<br>

# ➕ Adicionar Livro 
- Converte tudo para MAIÚSCULAS para padronizar.
- Valida se os campos não estão vazios.
- Mostra feedback animado após adicionar.
```java
System.out.print("\n📝 Informe o título do livro: ");
String titulo = scanner.nextLine().toUpperCase();

System.out.print("📝 Informe o autor(a): ");
String autor = scanner.nextLine().toUpperCase();

titulos.add(titulo);
autores.add(autor);
System.out.println("\n✅ SHOW! '" + titulo + "' foi adicionado com sucesso!");
```


<br>
<br>

# 🔍 Pesquisar Livro
- Busca por correspondência parcial (não precisa digitar o nome completo).
- Mostra a posição do livro na estante.
- Feedback visual quando encontra ou não o livro.
```java
for (int i = 0; i < titulos.size(); i++) {
    if (titulos.get(i).toLowerCase().contains(busca)) {
        System.out.println("\n🎉 ACHAMOS! 🎉");
        System.out.println("Título: " + titulos.get(i));
        System.out.println("✍Autor: " + autores.get(i));
    }
}
```

<br>
<br>

# ❌ Remover Livro
- Remove pelo título exato (case sensitive).
- Atualiza o contador de livros automaticamente.
```java
if (index != -1) {
    titulos.remove(index);
    autores.remove(index);
    System.out.println("\n💥 *POOF* 💥");
    System.out.println("   '" + livroRemovido + "' foi deletado com sucesso!");
}
```

<br>
<br>

# 📚 Listar todos os Livros
-Mostra todos os livros numerados.
- Formatação bonitinha com separadores.
- Mensagem especial quando a biblioteca está vazia.
```java
for (int i = 0; i < titulos.size(); i++) {
    System.out.println("📌 Posição " + (i + 1) + ":");
    System.out.println("📖 Título: " + titulos.get(i));
    System.out.println("✍️ Autor: " + autores.get(i));
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
