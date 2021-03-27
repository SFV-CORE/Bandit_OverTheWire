# Bandit - Over The Wire

# Tópicos 
 - Descrição
 - Direitos autorais
 - Níveis
      > Bandit 0 ao 33
 - Referências

 
## Descrição
  
   Bandit é um Capture The flag(CTF) voltado para o ensino, como funciona?
   É simples, a cada nível você terá que mostrar o que você sabe, caso tenha dúvidas, nos níveis tem os possiveis comandos que você irá usar.
   
   Os níveis tem instruções de como conseguir a senha para iniciar o proxímo nível.
   
   Como o intuito é aprender, este repositório não vai deixar as senhas mas sim explicar cada passo para completar os níveis e assim lhe ajudar.
   
   Obs: Para ter sentido, se você estiver lendo o nível e conseguiu entender uma parte atráves do tutorial, tenta terminar sozinho, afinal estamos aqui para aprender!

## Direitos autorais
  
   O provedor desse CTF é o https://overthewire.org/wargames/.
   Entra lá e da uma olhada caso não conheça, tem muita coisa legal.
   
   Tem diversos tutoriais para o bandit por ai, porém é tudo em inglês, achei uma ideia legal fazer em Pt/BR.
   Vou apresentar os metodos do meu jeito, então peço que não copiem a publicação...
   
   Caso tenha algo que peguei de outro site, irei colocar os respectivos direitos.
   Obrigado e espero que aproveitem!
 

# Níveis

## Bandit 0
  
 #### Título 
    O objetivo deste nível é que você entre no jogo usando SSH. O host ao qual você precisa se conectar é bandit.labs.overthewire.org, na porta 2220.
    
    O nome de usuario é bandit0 e a senha é bandit0.
    
    Uma vez conectado vá para a página Nível 1 para descobrir como vencer o Nível 1
    
#### Resolução
  Esse nível é um dos mais simples, só precisamos descobrir como fazer uma conexão com SSH.
  Para isso o game nos fornece 2 links muito úteis:
  > https://en.wikipedia.org/wiki/SSH_(Secure_Shell)
  
  > https://www.wikihow.com/Use-SSH
  
  Caso tenha lido e ainda tenha dúvidas, coloque no terminal
  
  > man ssh
  
  Este comando vai mostrar o manual de uso do comando ssh.
  
  Então vamos lá, a sintaxy para se conectar é a seguinte
  > ssh |nomeUsuario|@|servidor| -p |porta|
  
  O nível nos fala que o usuário é bandit0 e o servidor é bandit.labs.overthewire.org, a porta é simples, no lado superior esquerdo do site você virá a porta adequada.
  Com essas informações nosso comando fica assim:
  
  > ssh bandit5@bandit.labs.overthewire.org -p 2220
  
  Lembre-se de rodar no modo root, ou coloque sudo na frente.
  
  Logo em seguida vai pedir para colcoar a senha, sabemos que é bandit0.
  E pronto, estamos dentro!
  
  E agora o que fazer? Que tal vermos o que temos aqui?
  
  Escreva 
  > ls

  e de enter
  
  Achamos um arquivo, vamos ler ele.
  
  > cat readme
  
  E pronto, descobrimos a senha para o proxímo nível!
  
  Agora o que era os comandos que usamos?
  Vou explicar para você.
  
  *ls* nos mostra quais arquivos existem no diretório atual, ele tem diversas opções mas vamos ver mais para frente.
  
  *cat* serve para ler o arquvo selecionado, é útil em diversos momentos.
