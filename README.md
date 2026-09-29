
---

# Cadastro de Produtos em PHP

Este projeto é uma aplicação web simples desenvolvida em **PHP** e **MySQL** para o cadastro de produtos. O sistema conta com validações básicas e boas práticas de segurança, como o uso de **Prepared Statements** para prevenção de ataques de SQL Injection, além de prevenção de reenvio de formulário (padrão *Post/Redirect/Get*).

---

## 🚀 Funcionalidades

* **Cadastro de Produtos:** Interface em HTML para inserir o nome e o preço do produto.


* **Conexão com Banco de Dados:** Integração com MySQL utilizando a extensão `mysqli`.


* **Segurança contra SQL Injection:** Utilização de *Prepared Statements* (`bind_param`) nas consultas de inserção.


* **Prevenção de Duplicidade (PRG):** Utiliza o padrão *Post/Redirect/Get* para evitar que o formulário seja reenviado caso o utilizador atualize a página.


* **Validação de Campos:** Verificação tanto no front-end (`required`) quanto no back-end para garantir que os dados não estejam vazios.



---

## 🛠️ Tecnologias Utilizadas

* **PHP** (Processamento do lado do servidor)


* **MySQL** (Banco de dados relacional)


* **HTML5** (Estrutura da interface)



---

## ⚙️ Como Executar o Projeto

Para executar este projeto localmente, vais precisar de um servidor web com suporte a PHP e MySQL (como o **XAMPP**, **WampServer** ou **Laragon**).

1. **Clone o repositório ou descarregue os ficheiros:**
```bash
git clone https://github.com/o-seu-utilizador/o-seu-repositorio.git

```


2. **Configure o Banco de Dados:**
* Aceda ao seu gestor de banco de dados (ex: phpMyAdmin).
* Crie uma base de dados chamada `exercicio`.


* Crie a tabela `produtos` com a seguinte estrutura:
```sql
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    preco DECIMAL(10, 2) NOT NULL
);

```




3. **Configure a Conexão (se necessário):**
* No ficheiro do código PHP, as credenciais padrão de conexão estão configuradas da seguinte forma:


* Servidor: `localhost`

* Utilizador: `root`

* Palavra-passe: `Senai@118` *(Altere caso o seu ambiente utilize credenciais diferentes)*.






4. **Inicie o Servidor:**
* Coloque o ficheiro PHP na pasta raiz do seu servidor local (por exemplo, `htdocs` no XAMPP).
* Inicie os serviços do **Apache** e do **MySQL**.
* Aceda através do navegador (ex: `http://localhost/nome-do-ficheiro.php`).



---

## 📌 Exemplo de Código (Processamento)

Trecho do código responsável por validar e inserir os dados de forma segura no banco de dados:

```php
$stmt = $conn->prepare("INSERT INTO produtos (nome, preco) VALUES (?, ?)");
$stmt->bind_param("sd", $nome_produto, $preco);
$stmt->execute();

```
