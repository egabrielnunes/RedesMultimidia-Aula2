Exemplo Cliente e Servidor RTSP
----
Foi implementado um servidor de streaming vídeo e cliente que se comunica usando o protocolo de fluxo contínuo em tempo real (RTSP) e envia dados usando o protocolo de tempo real (RTP). 

Arquitetura
---
Este código possui 4 classes, que formam a arquitetura principal do sistema, são elas:

 1. **Client:** Esta classe implementa o cliente e a interface de usuário que é usado para enviar comandos RTSP e que será utilizada para exibir o vídeo. Abaixo vemos como é a interface. 

2. **Server:** Esta classe implementa o servidor que responde às requisições RTSP e encaminha o vídeo de volta. O servidor chama as rotinas na classe RTPpacket para empacotar os dados de vídeo.

3. **RTPpacket:** Esta classe é usada para manipular os pacotes RTP. Ela possui rotinas separadas para tratar os pacotes recebidos no lado cliente. 

4. **VideoStream:**  Esta classe é usada para ler os dados de vídeo do arquivo em disco. 

Executando o código 
----
É necessário compilar todos os arquivos .java, para isso iremos utilizar o comando abaixo:

```
$ make
```

Em seguida, é necessário executar o servidor e o cliente. 

```
$ ./run_server # executar o servidor
$ ./run_client # executar o cliente
```

Funcionamento
----

É possível enviar comandos RTSP para o servidor pressionando os botões. Uma interação normal RTSP acontece assim:


- O cliente envia **SETUP**. Esse comando é usado para ajustar os parâmetros de sessão e de transporte.
- O cliente envia **PLAY**. Isso inicia a reprodução.
- O cliente envia **PAUSE** se ele quiser pausar durante a reprodução.
- O cliente envia **CLOSE**.  Fecha a conexão.
-  O cliente envia **SESSION**. Isso termina a sessão.

![enter image description here](https://bit.ly/2vfU0vU)
