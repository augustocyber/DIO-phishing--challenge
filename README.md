# DIO-phishing--challenge

Este projeto tem objetivo educativo, conscientização de como é fácil gerar um link falso de phishing, sobre as práticas de phishing e demonstrar a capacidade de gerar estes, utilizando um ambiente controlado para testes éticos de segurança. Não é para ser usado de forma maliciosa ou ilegal.

## Descrição
As ferramentas usadas serão Social Engineering Toolkit (SeToolKit) que permite a criação de links de phishing e muito mais, sendo usada aqui para fins educativos, e o Zphisher que, assim como o SeToolkit, permite a criação de links de phishing para recuperar credenciais.
Este projeto destina-se a profissionais de segurança, pesquisadores e estudantes interessados em aprender sobre as ameaças de phishing e as medidas para combatê-las.
Como será usado para estudo, teste e aperfeiçoamento, serão utilizados somente IP interno nos testes.

## Ferramentas
* Kali Linux
* Terminal Linux
* SeToolKit
* Zphisher

## Atenção
* <b>Uso Responsável</b>: Antes de usar esta ferramenta, obtenha permissão explícita do proprietário do sistema ou vítima a ser testado.
* <b>Legislação</b>:Respeite as leis e regulamentos locais relacionados à segurança da informação e testes de penetração.
* <b>Propósito Educacional</b>:Este projeto destina-se exclusivamente a fins educativos e de treinamento em segurança da informação. Não use este projeto para atividades maliciosas.

## Como usar
Primeiramente tenha as ferramentas instaladas em seu sistema operacional. Siga o passo a passo de instalação das ferramentas nos sites correspondentes: <a href='https://github.com/trustedsec/social-engineer-toolkit' target="_blank">SeToolKit</a> e <a href='https://github.com/htr-tech/zphisher' target="_blank">Zphisher</a>
 Atente-se para o fato de o passo a passo será feito utilizando o Kali Linux virtualizado (WSL) e que as duas ferramentas são CLI (interfaces de linha de comando).
<br>
### Iniciaremos com o SetoolKit. 
A ferramenta é baseada em menus de seleção, como a ordem dos números pode alterar com o tempo, incluirei somente o nome da opção a selecionar. Caso queira explorar melhor as demais opções, a ferramenta possui uma documentação bem completa, não exite em lê-la:
1. Abra o terminal 
2. Digite: ```sudo su```
3. Digite sua senha na sequência
4. Agora digite: ```setoolkit```
5. A primeira opção do menu a ser selecionada será: ```Social-Engineering Attacks```
6. A segunda opção do menu a ser selecionada será: ```Website Attack Vectors```
7. A terceira opção do menu a ser selecionada será: ```Credential Harvester Attack Method```
8. A quarta eúltima opção do menu a ser selecionada será: ```Site cloner```
9. Ao apresentar um diálogo sobre o endereço de IP que será usado, pode só clicar no enter mesmo, pois a ferramenta detecta o IP da máquina e marca ela como default.

* Agora que vem a transformação do link. De acordo com a ferramenta, pode ser utilizado HTTP e HTTPS. No desafio foi utilizado o http://www.facebook.com, entretanto, provavelmente por alguma medida do Facebook, não está mais sendo possível (ao menos até o presente momento deste teste) realizar o clone de forma funcional do mesmo. Portanto iremos utilizar como exemplo o LinkedIn. 

10. Digite o link no terminal e de enter: https://www.linkedin.com/
11. Para acessar o clone e testar, use o ip address que foi usado na etapa ```9```.
12. Após logar, irá aparecer log bem extensos no terminal. E, por algum motivo, a obtenção do login não aparece em "USERNAME FIELD FOUND", mas sim em ```PARAM: session_key=<usuário digitado>``` que estará logo abaixo do primeiro ```[*] WE GOT A HIT! Printing the output:```

<br>

## Resultados do SeToolKit:
<img src="https://raw.githubusercontent.com/Albino-Marques/phishing-challenge-dio/main/assets/img/Linkedin.png" width='50%'>
<br>
<img src="https://raw.githubusercontent.com/Albino-Marques/phishing-challenge-dio/main/assets/img/Terminal-setoolkit.png" width='50%'>

<br>
<br>

[Arquivo de log do teste de ataque](https://github.com/Albino-Marques/phishing-challenge-dio/blob/main/assets/files/phishing-challenge-dio_log_setoolkit.txt)

<br>
<br>

### Agora usaremos o Zphisher:
Aassim como o SeToolKit, é uma ferramenta baseada em menus de seleção, então, também manterei apontando as opções usadas pelo texto, e não número da opção. Caso queira explorar melhor as demais opções, esta ferramenta também possui uma documentação bem completa, não exite em lê-la:
Com o Zphisher, está sendo possível clonar o facebook sem problemas. Utilizaremos ele para exemplo.
Após ter clonado o Zphisher como demonstra o site oficial, você fará o seguinte:
1. Abra a pasta do Zphisher: No meu caso ficou ```/home/albus/zphisher```, por tando uso ```cd zphisher/``` estando na pasta pessoal mesmo. 
2. Depois insida o comando: ```bash zphisher```
3. Irá aparecer várias opções possíveis de utilizarmos. Mas nos ateremos ao facebook. Digite os dois números correspondente ao ```facebook``` e de enter.
4. Agora iremos selecionar qual das páginas do facebook iremos clonar. No meu caso, selecionei a tradicional: ```Traditional Login Page```
5. Neste ponto, iremos perceber que inclusive podemos gerar um link falso pela web mesmo para poder enviar. Mas no momento iremos utilizar somente o ```Localhost```.
6. Será questionado se quer altera a porta. Digite ```N```.
7. Após isso ele irá abrirá uma tela com o seu localhost para clicar. Clicando será direcionado para a página fake do facebook. Os dados digitados irão aparecer nesta mesma tela do Zphisher.

## Resultados do Zphisher
<img src="https://raw.githubusercontent.com/Albino-Marques/phishing-challenge-dio/main/assets/img/Facebook.png" width='50%'>
<br>
<img src="https://raw.githubusercontent.com/Albino-Marques/phishing-challenge-dio/main/assets/img/Terminal-zphisher.png" width='50%'>

<br>
<br>

[Arquivo de log do teste de ataque](https://github.com/Albino-Marques/phishing-challenge-dio/blob/main/assets/files/phishing-challenge-dio_log_zphisher.txt)

<br>
<br>
