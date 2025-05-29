# Projeto Hello FastAPI - Testes

Este projeto é uma aplicação simples em FastAPI criada para fins de aprendizado e testes práticos envolvendo **Docker**, **Kubernetes (Kind)**, **Argo CD**, **GitHub Actions (CI/CD)** e testes automatizados com **Pytest**.

## Endpoints

- `/` : Retorna a mensagem "Hello World"
- `/square/{x}` : Retorna o quadrado do valor fornecido
- `/double/{x}` : Retorna o valor fornecido multiplicado por 2

## Etapas do Desenvolvimento

1. **Criação da VM:**
   - Criada VM Ubuntu.
   - Instalado o Kind (Kubernetes in Docker) e criado o cluster Kubernetes.

2. **Aplicação e Docker:**
   - Desenvolvida a API com FastAPI.
   - Criada a imagem Docker da aplicação.
   - Publicada a imagem no Docker Hub.

3. **Kubernetes:**
   - Criados os manifestos do Kubernetes: `Pod`, `Deployment`, `Service`.
   - Aplicação funcionando no cluster do Kind local.

4. **Argo CD:**
   - Instalado o Argo CD na VM.
   - Configurado o acesso via `kubectl port-forward`.
   - Sincronizado com o repositório do GitHub.
   - Criado o repositório `k8s/` com Kustomize (`deployment.yaml`, `service.yaml`, `kustomization.yaml`).

5. **GitHub Actions (CI/CD):**
   - Criado workflow em `.github/workflows/ci-cd.yml`.
   - Secrets configurados no repositório GitHub:
     - `DOCKERHUB_USERNAME`
     - `DOCKERHUB_TOKEN`

6. **Testes Automatizados:**
   - Workflow configurado para rodar os testes automaticamente durante o CI.
   - Dependências de teste instaladas via `requirements.txt`.
