## Descrição

Baseado no estudo de caso do pseudônimo **Toshiro Shibakita**, resolvemos o problema de criar uma aplicação que possibilita a utilização prática de **containers no cenário de microsserviços**.

## Objetivo

Através da **containerização**, inserir automaticamente **dados cadastrais de alunos em uma escola**, armazenados em um banco de dados via **aplicação web**.

A prática de containerização propicia a construção e desenvolvimento de uma **aplicação web portátil, escalável e independente**, gerando valor ao negócio da organização ao atender seus requisitos fundamentais.

## Descrição de cada componente

- **Container Docker para suporte à aplicação**
- **Banco de dados para cadastro de alunos**
- **Proxy utilizando NGINX**
- **Arquivo PHP para conexão da aplicação web com o banco de dados**

## Especificações técnicas dos componentes

1. **dockerfile** – *Criação de arquivo Docker para suporte à aplicação*  
   Responsável por **empacotar e executar a aplicação web** (ex.: PHP, Apache) de forma isolada, garantindo que todas as dependências necessárias estejam contidas no container e funcionando de forma consistente em qualquer ambiente.

2. **banco.sql** – *Banco de dados para cadastro de alunos*  
   Serviço de banco de dados (ex.: MySQL, MariaDB) rodando em um container separado, usado para **armazenar e gerenciar os dados dos alunos** (ID, nome, endereço, etc.), permitindo inserções, consultas, atualizações e exclusões.

3. **nginx.config** – *Criação de proxy utilizando NGINX*  
   Um container com **NGINX atuando como proxy reverso**, direcionando as requisições externas (HTTP) para o container da aplicação web, **melhorando o desempenho, segurança e gerenciamento de tráfego** da aplicação.

4. **index.php** – *Arquivo PHP para conexão da aplicação web com o banco de dados*  
   Script PHP que **faz a ponte entre a aplicação web e o banco de dados**, permitindo que a aplicação insira, consulte ou manipule os dados dos alunos via comandos SQL enviados do PHP para o banco. Esse servidor está hospedado via ambiente AWS. 

## Benefícios imediatos esperados na automatização do serviço

1. **Portabilidade entre ambientes**  
   O container garante que a aplicação rode **da mesma forma em qualquer servidor ou máquina**, seja no computador local, no datacenter ou na nuvem. Isso evita o clássico problema de “na minha máquina funciona”.

2. **Isolamento de aplicações**  
   Cada container roda de forma **isolada**, evitando que dependências ou configurações de uma aplicação interfiram em outra.

3. **Facilidade de escalabilidade e atualização**  
   É fácil **criar novas instâncias do container** para atender mais demanda, por exemplo, em um cenário escolar.  
   As atualizações podem ser feitas **sem impacto direto** no serviço: sobe-se uma nova versão do container e troca-se sem downtime perceptível.

4. **Automação de deploy e rollback**  
   Com Docker, o processo de **implantação pode ser automatizado** via scripts ou pipelines de CI/CD.  
   Caso uma atualização dê errado, é possível **voltar para a versão anterior rapidamente**, apenas substituindo o container.

5. **Redução de custos com infraestrutura**  
   Containers são mais **leves que máquinas virtuais**, usando menos recursos de CPU e memória.  
   Isso permite **rodar mais aplicações no mesmo hardware físico**, otimizando os custos.

6. **Consistência e confiabilidade**  
   Ao embalar o sistema dentro de um container, garante-se que **as mesmas dependências, bibliotecas e configurações estejam presentes**, evitando erros por ambientes diferentes.

Curta essa postagem!  

Me segue no linkedin:  [LinkedIn](https://www.linkedin.com/in/fabriciovieiira)