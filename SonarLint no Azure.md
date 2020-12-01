
## Usando o SonarLint no Azure

***

Através do SonarLint, que é uma extensão IDE que permite corrigir problemas de codificação, foi possível encontrar bugs e vulnerabilidades de segurança no código do Azure, que é um serviço que permite a empresas e desenvolvedores adquirirem as capacidades de processamento e armazenamento dos datacenters da Microsoft.   
Cada problema indicado pelo SonarLint possui uma das cinco severidades: _BLOCKER_, _CRITICAL_, _MAJOR_, _MINOR_, _INFO_.   
O BLOCKER detecta bug com alta probabilidade de afetar o comportamento do aplicativo em produção, como  problemas de vazamento de memória, conexão JDBC não fechada. 
Já o CRITICAL detecta bug com baixa probabilidade de afetar o comportamento do aplicativo em produção ou um problema que representa uma falha de segurança, por exemplo, bloco catch vazio, injeção de SQL. 
A severidade MAJOR indica uma falha de qualidade que pode impactar fortemente a produtividade do desenvolvedor, como pedaço descoberto de código, blocos duplicados, parâmetros não utilizados.   
Para a disciplina em questão vamos focar apenas nas três severidades descritas anteriormente. 
Analisando o package "com.azure.perf.test.core" do projeto, que possui 7 classes na linguagem java foi possível encontrar 30 problemas do tipo MAJOR, elas se deram devido a blocos catches e métodos vazios, falta do uso de construtores, uso de exceções genéricas como _RuntimeException_, que evita que os métodos tratem exceções verdadeiras geradas pelo sistema de maneira diferente dos erros gerados pelo aplicativo, se deram também por violação do princípio do encapsulamento e, por fim, variáveis que estão sendo declaradas em escopo externo. 

+++
title = "Exemplo de documento a ser produzido"
date = 2019-10-22
tags = []
categories = []
+++

***

Este é um documento guia para os alunos de Arquitetura de Software. A ideia é apresentar o modelo de documentação arquitetural que espero que seja produzido por eles. Esse guia foi baseado em um projeto chamado Parlametria, cujos detalhes arquiteturais estão descritos [aqui](https://docs.google.com/document/d/1OGPN7crENY5u9AiR_AE7Cb9rT92T-U-YppZL0m4TT2s/edit?usp=sharing).

O documento que você, aluno, deve produzir, deve seguir às diretrizes abaixo. Naturalmente, você pode adicionar, remover e alterar o formato, mas minha sugestão é que você mantenha o padrão que estou apresentando, inclusive, a mesma ordem e nomes de seções. Isso facilitará não só a padronização da documentação produzida por vocês.

***

# Autores

Este documento foi produzido por João Arthur Brunet.

- Matrícula: 857394857
- Contato: joao.arthur@computacao.ufcg.edu.br
- Projeto documentado: https://github.com/analytics-ufcg/parlametria-site

# Descrição Arquitetural -- Serviço de análise do twitter
