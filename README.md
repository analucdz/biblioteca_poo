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
- Esse programa é como um "sistema de bibliotecário virtual". Ele te deixa cadastrar livros, procurar livros pelo título, remover livros, e ver tudo o que já foi cadastrado. Tudo isso usando um menu simples no terminal.

<br>
<br>


# 📦 Classe Livro – A caixinha de informações do livro
```java
class Livro {
    private String titulo;
    private String autor;
    // ...
}
```
<br>
->  Cada vez que você cadastra um livro, você cria um novo objeto Livro com: <br>
* Um título <br>
* Um autor <br>
->  Ela também tem: <br>
* Getters pra pegar essas informações. <br>
* Um toString() que deixa o livro "bonitinho" quando a gente imprime: Título: O príncipe cruel | Autor: Holly Black <br>


<br>
<br>

# 🧠 Classe Biblioteca – O cérebro do sistema
## Aqui acontece toda a mágica. Ela tem:
- Uma lista (ArrayList<Livro>) que guarda todos os livros.
- Um scanner que lê o que você digita.
- Um menu que aparece em loop até você escolher sair.


<br>
<br>

# 📋 Método exibirMenu()
- Mostra o cardápio de opções pro usuário. É só aquele bloquinho que imprime:
```java
1. Adicionar Novo Livro
2. Pesquisar Livro por Título
...
```

    
<br>
<br>

# ➕ Método adicionarLivro()
- Aqui é onde você cadastra um novo livro.
1) Pede o título e autor.
2) Verifica se você não deixou nada em branco (obrigado, validação!).
3) Cria um novo Livro e joga na lista.
4) Dá aquele feedback bacana: "Novo livro cadastrado com sucesso!"


<br>
<br>

# 🔍 Método pesquisarLivro()
- Esse é o detetive do sistema 🕵️‍♂️.
1) Você digita o título que quer achar.
2) Ele percorre a lista toda.
3) Se encontrar, mostra as infos.
4) Se não, fala: "Livro não encontrado."


<br>
<br>

# ❌ Método excluirLivro()
- Aqui o sistema dá uma de destruidor (no bom sentido). 😅
1) Você digita o título que quer remover.
2) Ele procura na lista.
3) Se achar, remove o livro e avisa: "Livro excluído com sucesso!"
4) Se não, diz: "Operação falhou: livro não encontrado."


<br>
<br>

# 📚 Método listarLivros()
- Esse é o mais de boa. Ele só mostra tudo que está salvo.
1) Se não tiver nada: "Nenhum livro cadastrado."
2) Se tiver livros: ele imprime a lista toda, um por um.


<br>
<br>

# 🔁 O Loop principal (do...while)
- O sistema roda num loop infinito (quase), até você escolher a opção 5 - Sair. Toda vez que você escolhe uma opção, ele chama o método correspondente. Depois volta pro menu.


<br>
     <hr>
     <hr>


  ![eecf0ac7-3f37-4b8c-9d1b-a30660504d9d](https://github.com/user-attachments/assets/dffb81c8-3915-40fe-b279-784943908139)

</div>
