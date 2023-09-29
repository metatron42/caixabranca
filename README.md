# Qualidade de Software - Caixa Branca

Pelo o que eu consegui observar e analizar com o pedaço do codigo abordado em aula, identifiquei alguns problemas como:



1. **Erro na Classe `Class.forName`:**


   A linha `Class.forName("com.mysql.Driver.Manager").newInstance();` tem um erro. O nome correto da classe é `"com.mysql.cj.jdbc.Driver"`.

---

2. **Erro de Sintaxe SQL:**


   Há um erro de sintaxe na consulta SQL. Deveria haver espaços antes e depois das palavras-chave `where` e `and`. Além disso, faltou as aspas simples em torno da variável de senha na consulta SQL.

---

3. **Possível Exceção de Ponteiro Nulo:**


   Se ocorrer uma exceção ao estabelecer a conexão com o banco de dados, o método `conectarBD()` retornará `null`. Se você tentar usar essa conexão `null` no seu método `verificarUsuario`, resultará em uma `NullPointerException`.

---  

4. **Preocupações de Segurança:**


   Armazenar senhas em texto simples é um risco de segurança.
   
---
   
5. **Gerenciamento de Recursos:**


   Não está fechado os objetos `Connection`, `Statement` e `ResultSet` após usá-los.
