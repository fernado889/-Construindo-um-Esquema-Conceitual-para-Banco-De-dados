# -Construindo-um-Esquema-Conceitual-para-Banco-De-dados
-- Criando a tabela de Autores
CREATE TABLE Autores (
    AutorID INT PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Nacionalidade VARCHAR(50)
);

-- Criando a tabela de Livros
CREATE TABLE Livros (
    LivroID INT PRIMARY KEY,
    Titulo VARCHAR(200) NOT NULL,
    AutorID INT,
    AnoPublicacao INT,
    Genero VARCHAR(50),
    FOREIGN KEY (AutorID) REFERENCES Autores(AutorID)
);

-- Criando a tabela de Usuários
CREATE TABLE Usuarios (
    UsuarioID INT PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    DataCadastro DATE
);

-- Criando a tabela de Empréstimos
CREATE TABLE Emprestimos (
    EmprestimoID INT PRIMARY KEY,
    LivroID INT,
    UsuarioID INT,
    DataEmprestimo DATE,
    DataDevolucao DATE,
    FOREIGN KEY (LivroID) REFERENCES Livros(LivroID),
    FOREIGN KEY (UsuarioID) REFERENCES Usuarios(UsuarioID)
);
