# Тесты: Terraform

## Теория

### Вопросы

1. **Что такое state в Terraform?**
   - a) Состояние инфраструктуры
   - b) Состояние приложения
   - c) Состояние базы данных

2. **Какая команда применяет изменения?**
   - a) terraform plan
   - b) terraform apply
   - c) terraform deploy

3. **Что такое provisioner?**
   - a) Плагин
   - b) Поставщик облачной инфраструктуры
   - c) Выполняет действия на ресурсе

### Ответы
1. a) Состояние инфраструктуры
2. b) terraform apply
3. c) Выполняет действия на ресурсе

## Практика

### Задание 1: VPC Module

Создайте модуль VPC:
- Переменные: cidr, azs, name
- Outputs: vpc_id, public_subnet_ids
- Security groups

**Решение:**
```hcl
# variables.tf
variable "cidr" {
  description = "CIDR block"
  type        = string
  default     = "10.0.0.0/16"
}

variable "azs" {
  description = "Availability zones"
  type        = list(string)
  default     = ["us-east-1a", "us-east-1b"]
}

variable "name" {
  description = "Name tag"
  type        = string
  default     = "main"
}

# main.tf
resource "aws_vpc" "main" {
  cidr_block = var.cidr
  
  tags = {
    Name = var.name
  }
}

resource "aws_subnet" "public" {
  count = length(var.azs)
  
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(var.cidr, 8, count.index)
  availability_zone = var.azs[count.index]
  
  tags = {
    Name = "${var.name}-public-${count.index}"
  }
}

resource "aws_security_group" "main" {
  name        = "${var.name}-sg"
  description = "Main security group"
  vpc_id      = aws_vpc.main.id

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# outputs.tf
output "vpc_id" {
  value = aws_vpc.main.id
}

output "public_subnet_ids" {
  value = aws_subnet.public[*].id
}
```

### Задание 2: Remote State

Настройте remote state в S3:
- Backend конфигурация
- DynamoDB для блокировки
- Шифрование

**Решение:**
```hcl
# backend.tf
terraform {
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "prod/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"
    encrypt        = true
  }
}
```

## Самоконтроль

- [ ] Понимаю разницу между state и plan
- [ ] Умею писать модули
- [ ] Могу настроить remote state
- [ ] Понимаю работу provisioners