Executando Tarefas Automatizadas com AWS Lambda, S3 e LocalStack

 Introdução

Este projeto tem como objetivo demonstrar de forma prática como automatizar tarefas usando AWS Lambda e Amazon S3, tanto na AWS real quanto localmente com o LocalStack.
A ideia é entender o funcionamento desses serviços, suas vantagens e como eles se integram para executar processos automatizados sem necessidade de servidores.

Amazon S3 (Simple Storage Service)

O Amazon S3 é um serviço de armazenamento em nuvem que permite armazenar e acessar dados de forma segura, escalável e confiável.
Ele suporta qualquer tipo de arquivo — como vídeos, áudios, imagens e documentos — sendo ideal para backup, hospedagem de arquivos e armazenamento de objetos.

Um exemplo prático é quando realizamos exames médicos: os resultados ficam armazenados em nuvem, o que permite acessá-los rapidamente e de forma segura.
Por isso, o S3 é amplamente utilizado em sistemas que precisam garantir alta disponibilidade e durabilidade dos dados.

Vantagens do Amazon S3

Durabilidade: Altamente confiável, com redundância automática para proteger contra falhas.

Disponibilidade: Garante acesso contínuo aos dados.

Escalabilidade: Ajusta automaticamente a capacidade de armazenamento conforme a necessidade.

Segurança: Oferece criptografia, controle de acesso e monitoramento detalhado das atividades.

AWS Lambda

O AWS Lambda é um serviço de computação serverless que permite executar código em resposta a eventos, sem a necessidade de gerenciar servidores.
Basta fazer o upload do código e o Lambda se encarrega de executar, escalar e gerenciar automaticamente o processo.

Ele suporta diversas linguagens de programação como Python, Node.js, Java, C#, entre outras.

Vantagens do AWS Lambda

Execução sob demanda: Executa o código apenas quando necessário.

Escalabilidade automática: Ajusta automaticamente conforme o número de eventos.

Custo eficiente: Cobra apenas pelo tempo de execução e solicitações realizadas.

Integração com outros serviços AWS: Funciona junto com S3, DynamoDB, API Gateway, CloudWatch, entre outros.

Integração entre AWS Lambda e Amazon S3

O Lambda e o S3 podem ser integrados para automatizar tarefas baseadas em eventos.
Por exemplo: quando um novo arquivo é enviado ao S3, o evento dispara automaticamente uma função Lambda, que pode processar o arquivo, gerar logs, salvar informações em outro serviço ou enviar notificações.

Exemplo prático

Um usuário envia um arquivo para o bucket S3 (uploads/).

O evento de upload aciona a função Lambda.

O Lambda executa o código configurado (por exemplo, registrar o nome do arquivo, redimensionar uma imagem ou salvar dados no DynamoDB).

O resultado é armazenado novamente no S3 ou enviado para outro serviço AWS.

Fluxo resumido

Usuário → S3 → Evento → Lambda → CloudWatch (logs)


AWS Local com LocalStack

O LocalStack é uma ferramenta open source que permite simular localmente os serviços da AWS.
Isso facilita o desenvolvimento e os testes de aplicações sem precisar acessar a nuvem real, reduzindo custos e acelerando o processo.

Objetivo do LocalStack

Prover um ambiente local que simula os serviços da AWS para desenvolvimento, testes e integração contínua (CI/CD).

Versões disponíveis

Open Source (gratuita): Suporte básico a diversos serviços da AWS.

Pro e Enterprise: Suporte a recursos avançados e endpoints personalizados.

Serviços suportados

O LocalStack suporta vários serviços, incluindo:
Lambda, S3, API Gateway, DynamoDB, SNS, SQS, CloudFormation, entre outros.
