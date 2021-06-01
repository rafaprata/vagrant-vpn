# VPN com VMs

# Proposta do Projeto

Criar uma VPN utilizando o software OpenVPN entre duas máquinas virtuais locais. Subir as máquinas virtuais utilizando o Vagrant com Cloud Init e Imagem cloud. Documentando dia-a-dia cada passo dado.

# Passos do Projeto

- [x]  Criar Vagrantfile para provisionamento inicial de duas VMs.
- [x]  Criar um cloud-init.cfg para acessar cada uma das VMs.
- [x]  Definir uma das VMs como o servidor da VPN.
- [x]  Instalar o OpenVPN nas VMs.
- [ ]  Configurar a VPN seguindo os passos do [site](https://openvpn.net/community/).
- [ ]  Criar um roteiro para possível automação.
- [x]  Criar um repositório para controle de versão.
- [ ]  Desenvolver um provisionamento para cada uma das instalações.
- [ ]  Alterar o cloud-init.cfg de acordo com o provisionamento.
- [ ]  Criar um CI para realizar os testes.

# Documentação

- Domingo - 30/05

    Foi criada a página do projeto aqui dentro do Notion, além disso comecei a procurar como começar o Vagrantfile, baseado no [artigo](https://www.linkedin.com/pulse/se-preparando-para-o-kubernetes-122-felipe-miranda/) e no [github](https://github.com/FelipeMiranda/vagrant-kubernetes/blob/main/Vagrantfile) do Felipe Miranda. Comecei a definir as duas vms que serão utilizadas nesse projeto.

- Segunda-feira - 31/05

    Finalizado a criação inicial do Vagrantfile básico, duas máquinas Ubuntu 20.04 iniciadas baseada em uma cloud image ([https://cloud-images.ubuntu.com/](https://cloud-images.ubuntu.com/)). Além disso já foi criado um repositório no [github](https://github.com/rafaprata/vagrant-vpn) para acompanhar as alterações no projeto. Consegui desenvolver uma configuração de cloud-init básica para acesso via ssh, adicionando meu usuário e minha chave de acesso ssh. Finalizei a configuração de rede das máquinas, tendo em vista que uma das máquinas precisa ter acesso a internet, no caso utilizei conexão bridge pela interface WiFi, enquanto a outra terá acesso apenas pela VPN. Além disso já configurei o UserData.yml para instalar o OpenVPN nas VMs.

- Terça-feira - 01/06

    Ontem foi pensado criar uma terceira VM com o objetivo de cumprir o tutorial do site da [Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-set-up-and-configure-an-openvpn-server-on-ubuntu-20-04-pt), porém tendo em vista as dificuldades de comunicação entre as VM criadas pelo Vagrant, indicado no [artigo](https://www.linkedin.com/pulse/se-preparando-para-o-kubernetes-122-felipe-miranda/) do Felipe, tomei a decisão de fazer meu servidor CA e VPN a mesma máquina. Além disso foi necessário dar privilégios ao usuário criado pelo cloud-init.