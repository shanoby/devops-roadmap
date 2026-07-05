# Задание 1: VPC Module (Local)

## 🎯 Цель
Создать переиспользуемый Terraform модуль для локального тестирования.

## 📋 Задачи

### 1. Module structure
- [ ] variables.tf - cidr, name
- [ ] main.tf - Docker network, containers
- [ ] outputs.tf - network_id, container_names

### 2. Local testing
- [ ] Использовать Docker provider
- [ ] Создать сеть
- [ ] Запустить контейнеры

### 3. State management
- [ ] Локальный state
- [ ] Понимание state файлов
- [ ] State locking

## 🔧 Решение

```hcl
# variables.tf
variable "name" {
  description = "Network name"
  type        = string
  default     = "devops-network"
}

# main.tf
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 3.0"
    }
  }
}

resource "docker_network" "main" {
  name = var.name
}

resource "docker_container" "nginx" {
  image  = "nginx:alpine"
  name   = "web"
  networks = [
    {
      name = docker_network.main.name
    }
  ]
}

# outputs.tf
output "network_id" {
  value = docker_network.main.id
}

output "container_name" {
  value = docker_container.nginx.name
}
```

## ✅ Проверка
- [ ] Module создан
- [ ] State работает
- [ ] Network создан
- [ ] Container запущен
- [ ] Outputs возвращаются

## 📖 Документация
- [Terraform Docker Provider](https://registry.terraform.io/providers/kreuzwerker/docker/latest/docs)
- [Terraform Modules](https://developer.hashicorp.com/terraform/language/modules/develop)
- [Local State](https://developer.hashicorp.com/terraform/language/settings/backends/local)