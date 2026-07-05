# 9. Infrastructure as Code

## 🎯 Что изучить

### Terraform
- Providers, Resources, Variables, Outputs
- State management (local, remote)
- Modules
- Workspaces
- Functions (templatefile, lookup, coalesce)

### Ansible
- Playbooks, Roles, Tasks
- Inventory (static, dynamic)
- Handlers, Templates (Jinja2)
- Variables, Facts

### Packer
- Builders, Provisioners
- Templates
- HCL2

## 📖 Документация
- [Terraform Registry](https://registry.terraform.io/)
- [Learn Terraform](https://learn.hashicorp.com/terraform)
- [Ansible Documentation](https://docs.ansible.com/)

## ✅ Тесты для самоконтроля

### Тест 1: Terraform
```hcl
# Создайте модуль VPC:
# - Переменные: cidr, azs, name
# - Outputs: vpc_id, subnet_ids
# - Security groups
# - Remote state в S3
```

### Тест 2: Ansible
- Playbook для настройки сервера
- Role для nginx
- Шаблоны конфигураций

## 📁 Практические задания
- [Задание 1: VPC Module](exercises/vpc-module.md)
- [Задание 2: Ansible Playbook](exercises/ansible-playbook.md)