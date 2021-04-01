# Bandit - Over The Wire

# Tópicos 
 - Descrição
 - Direitos autorais
 - Níveis
      > Bandit 0 ao 33
 - Referências

 
## Descrição
  
   Bandit é um Capture The flag(CTF) voltado para o ensino, como funciona?
   É simples, a cada nível você terá que mostrar o que você sabe, caso tenha dúvidas, nos níveis tem os possíveis comandos que você irá usar.
   
   Os níveis têm instruções de como conseguir a senha para iniciar o próximo nível.
   
   Como o intuito é aprender, este repositório não vai deixar as senhas, mas sim explicar cada passo para completar os níveis e assim lhe ajudar.
   
   Obs: Para ter sentido, se você estiver lendo o nível e conseguiu entender uma parte através do tutorial, tenta terminar sozinho, afinal estamos aqui para aprender!
   
   Quando aparecer
   
   > isso 
   
   Significa que é um comando para usar.

## Direitos autorais
  
   O provedor desse CTF é o https://overthewire.org/wargames/.
   Entra lá e dá uma olhada caso não conheça, tem muita coisa legal.
   
   Tem diversos tutoriais para o bandit por aí, porém é tudo em inglês, achei uma ideia legal fazer em Pt/BR.
   Vou apresentar os métodos do meu jeito, então peço que não copiem a publicação...
   
   Caso tenha algo que peguei de outro site, irei colocar os respectivos direitos.
   Obrigado e espero que aproveitem!
 

# Níveis

## Bandit 0
  
 #### Título 
    O objetivo deste nível é que você entre no jogo usando SSH. O host ao qual você precisa se conectar é bandit.labs.overthewire.org, na porta 2220.
    
    O nome de usuário é bandit0 e a senha é bandit0.
    
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
  
  > ssh bandit0@bandit.labs.overthewire.org -p 2220
  
  Lembre-se de rodar no modo root, ou coloque sudo na frente.
  
  Logo em seguida vai pedir para colocar a senha, sabemos que é bandit0.
  E pronto, estamos dentro!
  
  E agora o que fazer? Que tal vermos o que temos aqui?
  
  Escreva 
  > ls

  e de enter
  
  Achamos um arquivo, vamos ler ele.
  
  > cat readme
  
  E pronto, descobrimos a senha para o próximo nível!
  
  Agora o que era os comandos que usamos?
  Vou explicar para você.
  
  *ls* nos mostra quais arquivos existem no diretório atual, ele tem diversas opções mas vamos ver mais para frente.
  
  *cat* serve para ler o arquivo selecionado, é útil em diversos momentos.

## Bandit 1
  
 #### Título 
    A senha para o próximo nível é armazenada em um arquivo chamado - localizado no diretório inicial
    
#### Resolução

  Primeiro vamos fazer a conexão:
  
  > ssh bandit1@bandit.labs.overthewire.org -p 2220
  
  > senha...
  
  Como padrão sempre vemos o que tem no diretório atual:
  
  > ls -al

  Achamos o arquivo que o nível informou " - ", vamos ler ele.
  
  > cat ./-
  
  E pronto, descobrimos a senha para o próximo nível!
  
  O cat já sabemos para que serve, mas por que precisamos usar o ./ para ler esse arquivo?
  
  A resposta é simples, como - é um caractere especial usado para as opções do comando, usá-lo no cat nos traria problemas. Exemplo: ls -al
  
  Se escrevermos cat - iria retornar nada e ficaríamos esperando eternamente, pode fazer o teste ver por si mesmo, para sair é só usar o crtl + z
  
  Agora que temos a senha, vamos para o próximo nível!
