# Documenta-o-do-Programa-de-Gerenciamento-de-Biblioteca

# Explicação do Código

## Classes Bases:
ItemBiblioteca: Classe base que representa um item na biblioteca com o atributo titulo.

Livro: Herda de ItemBiblioteca e adiciona atributos específicos como autor e isbn.

Usuario: Herda de ItemBiblioteca e adiciona o atributo matricula.

## Classe Biblioteca:
Armazena listas de livros e usuários.

Métodos para adicionar livros e usuários às respectivas listas.

## Classe GerenciadorDePedidos:
Gerencia os pedidos de livros feitos pelos usuários.

Método solicitar_livro para adicionar um pedido se o livro estiver disponível.

## Classe BibliotecaApp:
Responsável pela interface gráfica utilizando tkinter.

Contém métodos para cadastrar livros e usuários, visualizar listas e navegar entre diferentes telas.


# 1. Diagrama UML
![image](https://github.com/user-attachments/assets/998091b1-c08c-4012-ac67-8c8d862d4b75)

ItemBiblioteca
Atributos:
titulo: str
Métodos:
__init__(self, titulo)
Livro (Herda de ItemBiblioteca)

Atributos:
autor: str
isbn: str
Métodos:
__init__(self, titulo, autor, isbn)
Usuario (Herda de ItemBiblioteca)

Atributos:
matricula: str
Métodos:
__init__(self, nome, matricula)
Biblioteca

Atributos:
livros: List[Livro]
usuarios: List[Usuario]
Métodos:
__init__(self)
adicionar_livro(self, livro: Livro)
adicionar_usuario(self, usuario: Usuario)
GerenciadorDePedidos

Atributos:
biblioteca: Biblioteca
pedidos: List[Tuple[Usuario, Livro]]
Métodos:
__init__(self, biblioteca: Biblioteca)
solicitar_livro(self, usuario: Usuario, livro: Livro) -> bool
BibliotecaApp

Atributos:
root: Tk
biblioteca: Biblioteca
main_frame: Frame
Botões para cadastro e visualização
Métodos:
__init__(self, root: Tk)
cadastro_livro(self)
cadastro_usuario(self)
visualizar_livros(self)
visualizar_usuarios(self)
voltar(self, frame: Frame)
Relações:
Livro e Usuario herdam de ItemBiblioteca.
Biblioteca contém listas de Livro e Usuario.
GerenciadorDePedidos depende de Biblioteca.
BibliotecaApp interage com Biblioteca para gerenciar livros e usuários.



# 2. Documentação das Classes e Métodos
#Classe ItemBiblioteca
Descrição: Classe base que representa um item genérico na biblioteca.
Atributos:
titulo (str): O título do item.
Métodos:
__init__(self, titulo): Inicializa o atributo titulo.

## Classe Livro
Descrição: Representa um livro na biblioteca.
Atributos:
autor (str): O autor do livro.
isbn (str): O número ISBN do livro.
Métodos:
__init__(self, titulo, autor, isbn): Inicializa os atributos titulo, autor e isbn.

## Classe Usuario
Descrição: Representa um usuário da biblioteca.
Atributos:
matricula (str): A matrícula do usuário.
Métodos:
__init__(self, nome, matricula): Inicializa os atributos nome (herdado como titulo) e matricula.

## Classe Biblioteca
Descrição: Gerencia a coleção de livros e usuários da biblioteca.
Atributos:
livros (List[Livro]): Lista de livros cadastrados.
usuarios (List[Usuario]): Lista de usuários cadastrados.
Métodos:
__init__(self): Inicializa as listas de livros e usuários vazias.
adicionar_livro(self, livro: Livro): Adiciona um livro à lista de livros.
adicionar_usuario(self, usuario: Usuario): Adiciona um usuário à lista de usuários.

## Classe GerenciadorDePedidos
Descrição: Gerencia os pedidos de livros feitos pelos usuários.
Atributos:
biblioteca (Biblioteca): Referência à instância da biblioteca.
pedidos (List[Tuple[Usuario, Livro]]): Lista de pedidos realizados.
Métodos:
__init__(self, biblioteca: Biblioteca): Inicializa com uma referência à biblioteca e uma lista de pedidos vazia.
solicitar_livro(self, usuario: Usuario, livro: Livro) -> bool: Adiciona um pedido se o livro estiver disponível e retorna True. Caso contrário, retorna False.

## Classe BibliotecaApp
Descrição: Responsável pela interface gráfica do Gerenciador de Biblioteca.
Atributos:
root (Tk): A janela principal do aplicativo.
biblioteca (Biblioteca): Instância da classe Biblioteca para gerenciar dados.
main_frame (Frame): Frame principal contendo os botões de navegação.
Métodos:
__init__(self, root: Tk): Configura a interface gráfica inicial com botões para cadastrar e visualizar livros e usuários.
cadastro_livro(self): Abre a tela de cadastro de livros.
cadastro_usuario(self): Abre a tela de cadastro de usuários.
visualizar_livros(self): Exibe a lista de livros cadastrados.
visualizar_usuarios(self): Exibe a lista de usuários cadastrados.
voltar(self, frame: Frame): Retorna à tela principal a partir de uma tela específica.

# 3. Descrição das Funcionalidades
## Cadastro de Livros:
Permite ao usuário inserir o título, autor e ISBN de um novo livro.
Ao salvar, o livro é adicionado à lista de livros da biblioteca.

## Cadastro de Usuários:
Permite ao usuário inserir o nome e matrícula de um novo usuário.
Ao salvar, o usuário é adicionado à lista de usuários da biblioteca.

## Visualização de Livros:
Exibe uma lista de todos os livros cadastrados, mostrando título, autor e ISBN

## Visualização de Usuários:
Exibe uma lista de todos os usuários cadastrados, mostrando nome e matrícula.

## Navegação Entre Telas:
Botões permitem navegar entre as diferentes funcionalidades.
Botões de "Voltar" permitem retornar à tela principal a partir de qualquer tela específica.

# 4. Roadmap de Execução
Inicialização do Programa:
O programa começa executando a classe BibliotecaApp dentro do bloco if __name__ == "__main__":.
Cria a janela principal (root) e instancia BibliotecaApp.
Tela Principal:
Apresenta botões para:
Cadastrar Livro
Cadastrar Usuário
Visualizar Livros
Visualizar Usuários
Cadastro de Livro:
Ao clicar em "Cadastrar Livro", a tela principal é escondida.
Apresenta campos para inserir título, autor e ISBN.
Ao salvar, cria uma instância de Livro e adiciona à lista de livros na Biblioteca.
Retorna à tela principal.
Cadastro de Usuário:
Similar ao cadastro de livro, permite inserir nome e matrícula.
Cria uma instância de Usuario e adiciona à lista de usuários na Biblioteca.
Retorna à tela principal.
