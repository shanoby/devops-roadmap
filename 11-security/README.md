# 11. Безопасность

## 🎯 Что изучить

### DevSecOps
- **SAST** - SonarQube, Checkmarx, Semgrep (статический анализ)
- **DAST** - OWASP ZAP, Burp Suite (динамический анализ)
- **Container scanning** - Trivy, Clair, Snyk, Docker Scout
- **Dependency scanning** - Dependabot, Snyk, OWASP Dependency Check
- **Policy as Code** - OPA (Open Policy Agent), Kyverno, Kyverno

### Secrets Management
- **HashiCorp Vault** - KV store, Transit, Dynamic secrets, Auth methods
- **Kubernetes Secrets** - создание, использование, encryption
- **AWS Secrets Manager, Parameter Store** - хранение, ротация
- **Azure Key Vault** - сертификаты, ключи, секреты
- **GCP Secret Manager** - версии, IAM

## 📖 Документация
- [Vault Documentation](https://www.vaultproject.io/docs) - официальная документация
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) - уязвимости
- [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks/) - hardening
- [Trivy Docs](https://aquasecurity.github.io/trivy/) - сканер
- [OPA Docs](https://www.openpolicyagent.org/docs/) - policy as code

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: DevSecOps
- [ ] Понимаю SAST и DAST
- [ ] Могу выполнить container scanning
- [ ] Понимаю dependency scanning
- [ ] Понимаю policy as code
- [ ] Понимаю security в CI/CD

### Чекпоинт 2: Secrets
- [ ] Понимаю Vault KV store
- [ ] Могу создать dynamic secrets
- [ ] Понимаю Kubernetes Secrets
- [ ] Понимаю AWS Secrets Manager
- [ ] Понимаю encryption at rest

### Чекпоинт 3: Hardening
- [ ] Понимаю CIS benchmarks
- [ ] Могу настроить security headers
- [ ] Понимаю network policies
- [ ] Понимаю pod security standards
- [ ] Понимаю image scanning

## 📁 Практические задания
- [Задание 1: Container Scanning](exercises/container-scanning.md)
- [Задание 2: Secrets Management](exercises/secrets-management.md)