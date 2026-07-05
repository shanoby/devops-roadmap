# 9. Infrastructure as Code

## 🎯 Что изучить

### Terraform
- **Providers** - AWS, Azure, GCP, Kubernetes, Helm
- **Resources** - создание инфраструктуры
- **Variables** - input, output, locals
- **State management** - local, remote (S3, GCS, Terraform Cloud)
- **Modules** - создание, использование, registry
- **Workspaces** - окружения
- **Functions** - templatefile, lookup, coalesce, join, split
- **Data sources** - чтение существующих ресурсов

### Ansible
- **Playbooks** - YAML, tasks, handlers
- **Roles** - структура, defaults, vars, templates
- **Inventory** - static, dynamic, groups
- **Handlers, Templates** - Jinja2, notify
- **Variables, Facts** - host vars, group vars, magic variables
- **Modules** - cloud, system, network

### Packer
- **Builders** - Amazon, Azure, Google, Docker
- **Provisioners** - shell, file, ansible, chef, puppet
- **Templates** - HCL2, variables, functions
- **Post-processors** - docker-tag, docker-push

## 📖 Документация
- [Terraform Registry](https://registry.terraform.io/) - провайдеры и модули
- [Learn Terraform](https://learn.hashicorp.com/terraform) - интерактивные уроки
- [Ansible Documentation](https://docs.ansible.com/) - официальная документация
- [Ansible Galaxy](https://galaxy.ansible.com/) - роли
- [Packer Docs](https://www.packer.io/docs) - официальная документация

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Terraform
- [ ] Понимаю providers и resources
- [ ] Могу писать variables и outputs
- [ ] Понимаю state management
- [ ] Могу создавать модули
- [ ] Понимаю workspaces

### Чекпоинт 2: Ansible
- [ ] Понимаю playbook structure
- [ ] Могу создавать roles
- [ ] Понимаю inventory
- [ ] Могу использовать templates (Jinja2)
- [ ] Понимаю handlers

### Чекпоинт 3: Packer
- [ ] Понимаю builders
- [ ] Могу использовать provisioners
- [ ] Понимаю HCL2
- [ ] Могу создавать image pipeline

## 📁 Практические задания
- [Задание 1: VPC Module](exercises/vpc-module.md)
- [Задание 2: Ansible Playbook](exercises/ansible-playbook.md)