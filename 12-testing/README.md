# 12. Тестирование

## 🎯 Что изучить

### Тестирование инфраструктуры
- **Terratest** - Go-based testing, terraform, kubernetes, AWS
- **KitchenCI** - Test Kitchen, kitchen-terraform, kitchen-docker
- **InSpec** - compliance testing, CIS benchmarks, custom profiles
- **Serverspec** - RSpec tests for infrastructure

### Chaos Engineering
- **Chaos Monkey** - Netflix OSS, random termination
- **Litmus** - Kubernetes native, chaos experiments
- **Gremlin** - commercial, various attack types
- **Chaos Mesh** - Kubernetes, pod, network, stress chaos

## 📖 Документация
- [Terratest](https://terratest.gruntwork.io/) - тестирование Terraform
- [Chaos Engineering](https://principlesofchaos.org/) - принципы
- [Test Kitchen](https://docs.chef.io/kitchen/) - тестирование Chef
- [InSpec](https://docs.chef.io/inspec/) - compliance
- [Litmus Docs](https://litmuschaos.io/docs/) - Kubernetes chaos

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Terratest
- [ ] Понимаю Go basics (functions, structs, testing)
- [ ] Могу писать тесты для Terraform
- [ ] Понимаю terraform.Options
- [ ] Могу проверять созданные ресурсы
- [ ] Понимаю cleanup

### Чекпоинт 2: InSpec
- [ ] Понимаю RSpec синтаксис
- [ ] Могу писать контролы
- [ ] Понимаю CIS benchmarks
- [ ] Могу запускать тесты
- [ ] Понимаю отчеты

### Чекпоинт 3: Chaos
- [ ] Понимаю chaos engineering принципы
- [ ] Могу создать chaos эксперимент
- [ ] Понимаю pod deletion сценарий
- [ ] Понимаю network latency сценарий
- [ ] Понимаю анализ результатов

## 📁 Практические задания
- [Задание 1: Infrastructure Tests](exercises/infrastructure-tests.md)
- [Задание 2: Chaos Engineering](exercises/chaos-engineering.md)