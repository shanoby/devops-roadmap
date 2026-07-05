# 11. Безопасность

## 🎯 Что изучить

### DevSecOps
- SAST (SonarQube, Checkmarx)
- DAST (OWASP ZAP, Burp Suite)
- Container scanning (Trivy, Clair, Snyk)
- Dependency scanning
- Policy as Code (OPA, Kyverno)

### Secrets Management
- HashiCorp Vault (KV, Transit, Dynamic secrets)
- Kubernetes Secrets
- AWS Secrets Manager, Parameter Store
- Azure Key Vault
- GCP Secret Manager

## 📖 Документация
- [Vault Documentation](https://www.vaultproject.io/docs)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks/)

## ✅ Тесты для самоконтроля

### Тест 1: Scanning
- Trivy сканирование образов
- Интеграция в CI/CD
- Блок захвата уязвимых образов

### Тест 2: Vault
- Установить Vault
- Хранить secrets
- Динамические credentials для БД

## 📁 Практические задания
- [Задание 1: Container Scanning](exercises/container-scanning.md)
- [Задание 2: Secrets Management](exercises/secrets-management.md)