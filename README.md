# Tech Challenge - Fase 2

O presente repositório compoem a execução do desafio técnico definido para a segunda fase da Pós-graduação em Arquiteturade Sistemas .NET com Azure.

## Objetivos do Desafio
- Testes de Integração: assegurar que os componentes do sistema funcionem corretamente quando integrados.
- Integração Contínua (CI) com GitHub Actions: automatizar testes unitários, testes de integração e build.
- Monitoramento com Prometheus e Grafana: implementar métricas para monitorar a saúde e o desempenho do aplicativo (é possível utilizar o Docker local para esta etapa).

## Composição do Projeto
O Projeto encontra-se dividido em três repositórios presentes na plaforma e citados abaixo:
- **ArquivosCompose:** possui os arquivos para build e deploy dos demais;
- **[CadastroTech](https://github.com/antonioAlmeida95/CadastroTech "CadastroTech"):** repositório contendo a API em dotnet core a ser monitorada;
- **[Prometheus](https://github.com/antonioAlmeida95/Prometheus "Prometheus"):** responsável por conter os arquivos básicos para configuração e execução via docker do servidor de monitoramento Prometheus;
- **[Grafana](https://github.com/antonioAlmeida95/Grafana "Grafana"):**: contém os arquivos básicos para configuração e execução via docker do servidor Grafana;

## Deploy

Para fazer o deploy do projeto como todo é necessário ter baixado os demais repositórios, e manter o arquivo `docker-compose.yml` na raiz do direttório o qual encontra-se os outros. Para o arquivo `init.sql` é necessário criar duas pastas, uma com o nome `postgres` e mover o arquivo para lá, e uma pasta vazia com o nome `data` dentro da primeira, abaixo encontra-se a disposição dos direttórios:

```
|- CadastroTech
|- Grafana
|- Prometheus
|- postgres
|-- data
|-- init.sql
|- docker-compose.yml
```
Após os ajustes na disposição dos arquivos do repositório (ArquivosCompose), basta executar o comando:

```bash
  docker-compose up --build
```
