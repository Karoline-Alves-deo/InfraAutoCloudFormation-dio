# Implementando Infraestrutura Automatizada com AWS CloudFormation

## Descrição
Este desafio tem como objetivo **implementar uma infraestrutura automatizada** utilizando o AWS CloudFormation.  
A proposta é criar e gerenciar recursos na nuvem por meio de templates em YAML ou JSON, aplicando os conceitos de Infraestrutura como Código (IaC), padronização, replicação e segurança.

Durante a prática, o aluno deve explorar a automação do provisionamento de serviços na AWS, simulando cenários reais de implantação e gerenciamento de recursos.

---

##  Objetivos de Aprendizagem

- Aplicar os conceitos aprendidos em um ambiente prático;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica;
- Entender os benefícios da automação de infraestrutura com AWS CloudFormation.

---


## Template CloudFormation (`template.yaml`)

    AWSTemplateFormatVersion: "2010-09-09"
    Description: "Infraestrutura básica automatizada com AWS CloudFormation"

    Resources:
      MyS3Bucket:
        Type: AWS::S3::Bucket
        Properties:
          BucketName: !Sub "bucket-dio-cloudformation-${AWS::AccountId}"
          VersioningConfiguration:
            Status: Enabled

      MyEC2Instance:
        Type: AWS::EC2::Instance
        Properties:
          InstanceType: t2.micro
          ImageId: ami-0c55b159cbfafe1f0
          Tags:
            - Key: name
              Value: "Instancia-CloudFormation"

---

## Conceitos Aplicados

- Infraestrutura como Código (IaC): padronização e automação de recursos;  
- Reprodutibilidade: criação de ambientes idênticos em diferentes contas;  
- Escalabilidade e Segurança: gestão centralizada de configurações;  
- Automação de Deploys: integração com pipelines de CI/CD.

---

## Como Executei

1. Fiz login no console da AWS.  
2. Acessei CloudFormation → Create Stack.  
3. Fiz upload do arquivo `template.yaml`.  
4. Cliquei em Next, preenchi as opções e finalizei com Create Stack.  
5. Após a execução, verifiquei os recursos criados (S3, EC2 etc).  
6. Para remover tudo: deletei a stack no CloudFormation (isso remove os recursos criados pelo template).

---

## Insights e Aprendizados

Durante o desenvolvimento deste desafio, foram explorados:

- A importância da automação para reduzir erros humanos;  
- Como templates YAML tornam a infraestrutura mais transparente e versionável;  
- O potencial de integração do CloudFormation com outros serviços AWS, como Lambda, IAM e S3;  
- Boas práticas: parametrizar valores, usar Outputs úteis, documentar dependências e cuidar de políticas IAM.

---

## Autora 

**Karoline Alves**

Entusiasta em tecnologia, robótica e computação em nuvem.
