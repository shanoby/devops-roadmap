# Задание 1: VPC Module

## 🎯 Цель
Создать переиспользуемый Terraform модуль для VPC.

## 📋 Задачи

### 1. Module structure
- [ ] variables.tf - cidr, azs, name
- [ ] main.tf - VPC, subnets, security groups
- [ ] outputs.tf - vpc_id, subnet_ids

### 2. Remote state
- [ ] Настроить S3 backend
- [ ] DynamoDB для блокировки
- [ ] Шифрование

### 3. Security
- [ ] Security groups
- [ ] NAT gateway
- [ ] Internet gateway

## 🔧 Решение

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

# main.tf
resource "aws_vpc" "main" {
  cidr_block = var.cidr
  tags = {
    Name = var.name
  }
}

resource "aws_subnet" "public" {
  count = length(var.azs)
  vpc_id = aws_vpc.main.id
  cidr_block = cidrsubnet(var.cidr, 8, count.index)
  availability_zone = var.azs[count.index]
}

# outputs.tf
output "vpc_id" {
  value = aws_vpc.main.id
}
```

## ✅ Проверка
- [ ] Module создан
- [ ] Remote state работает
- [ ] Security groups настроены
- [ ] Outputs возвращаются
- [ ] Module переиспользуем

## 📖 Документация
- [Terraform Modules](https://developer.hashicorp.com/terraform/language/modules/develop)
- [AWS VPC Module](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)