# Projeto de Arquitetura AWS: Site Dinâmico

Este repositório documenta a arquitetura de um site dinâmico hospedado na AWS, utilizando serviços essenciais de computação e rede.

---

## Diagrama da Arquitetura

(diagrama.png)

## Componentes da Arquitetura

Este projeto utiliza os seguintes serviços da AWS, cada um com um papel específico no funcionamento da aplicação:

- *Internet:* Representa os usuários acessando o site de qualquer lugar do mundo.
- *Serviço de Domínio (Route 53):* Direciona o nome de domínio (como www.exemplo.com) para o seu servidor na AWS.
- *Gateway de Internet (Internet Gateway):* Permite que o tráfego da internet pública entre na sua rede privada (VPC).
- *Sua Rede na Nuvem (VPC):* Uma rede virtual isolada e segura na nuvem da AWS onde seus recursos estão localizados.
- *Firewall Virtual (Security Group):* Atua como um firewall, controlando qual tráfego pode chegar à sua instância EC2.
- *Servidor Web (EC2):* Uma máquina virtual que hospeda o código e os arquivos do seu site dinâmico.
- *Disco de Armazenamento (EBS):* O disco rígido virtual que é conectado ao seu servidor EC2 para armazenamento de dados persistente.

---

## O Fluxo de Tráfego

O diagrama visualiza o seguinte fluxo de dados:

1.  Um usuário na *Internet* digita o endereço do site, e a requisição é enviada para o *Serviço de Domínio (Route 53)*.
2.  O *Route 53* direciona a requisição para o *Gateway de Internet, permitindo que ela entre na sua **VPC*.
3.  Dentro da VPC, o *Firewall Virtual (Security Group)* verifica se a requisição é segura.
4.  Se for aprovada, a requisição chega ao *Servidor Web (EC2), que usa o **Disco de Armazenamento (EBS)* para carregar a página e enviá-la de volta ao usuário.
   
