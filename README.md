# Hi, I'm Mitchell 👋  
**Senior Network Engineer | Cloud Architect | Owner of Designer Technologies LLC**

I design and build resilient network and cloud infrastructures with a focus on AWS, Azure, automation, and high‑availability architectures. I also run Designer Technologies LLC, delivering IT consulting, cloud migrations, and small‑business infrastructure solutions.

## 🚀 What I Do
- Cloud networking (AWS + Azure)
- VPC design, Transit Gateway, hybrid networking
- Enterprise routing, switching, firewalls
- DNS architecture (Azure DNS, Route 53, BIND, Windows DNS)

## 🛠️ Tech Stack
- **Cloud:** AWS, Azure  
- **Infra:** Terraform, Ansible, Docker  
- **Networking:** Cisco, Fortinet, Palo Alto, Meraki   
- **Languages:** Python, PowerShell 

## 📈 Current Goals
- AWS Solutions Architect Certification  
- Growing Designer Technologies LLC  
- Building cloud‑native automation frameworks  
- Terraform IaC for scalable deployments  

## 📫 Connect With Me
- Website: designertechnologies.net  
- Email: info@designertechnologies.net  

---

## 🔧 Tech & Tools

![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Cisco](https://img.shields.io/badge/Cisco-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)

---

## ☁️ AWS Cloud Showcase

Below is a simple AWS VPC example demonstrating core networking concepts using Terraform:

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_support   = true
  enable_dns_hostnames = true
  tags = { Name = "example-vpc" }
}

resource "aws_internet_gateway" "igw" {
  vpc_id = aws_vpc.main.id
  tags = { Name = "example-igw" }
}

resource "aws_subnet" "public_a" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  availability_zone       = "us-east-1a"
  map_public_ip_on_launch = true
  tags = { Name = "public-a" }
}

resource "aws_route_table" "public_rt" {
  vpc_id = aws_vpc.main.id
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.igw.id
  }
  tags = { Name = "public-rt" }
}

resource "aws_route_table_association" "public_assoc" {
  subnet_id      = aws_subnet.public_a.id
  route_table_id = aws_route_table.public_rt.id
}

## 📘 What This Code Is

This profile includes examples written in **Markdown** and **Terraform (HCL)** to showcase my AWS cloud networking and Infrastructure‑as‑Code skills.

### 📝 Markdown (GitHub Profile Formatting)
All sections, headings, badges, and descriptions in this README are written in **Markdown**, which GitHub automatically formats into a clean visual layout.  
Markdown is used for:
- Headings (`#`, `##`)
- Lists (`- item`)
- Badges (image links)
- Section dividers (`---`)
- Code blocks (triple backticks)

### ☁️ Terraform for AWS (Infrastructure as Code)
The AWS example in this profile is written in **Terraform**, using **HCL (HashiCorp Configuration Language)**.  
Terraform is used to:
- Build AWS cloud networks (VPCs, subnets, route tables)
- Automate infrastructure deployments
- Create repeatable, version-controlled cloud environments
- Enforce consistent architecture across dev/stage/prod

### 🔧 AWS Example (Terraform)
Shows how to build:
- VPC  
- Subnets  
- Internet Gateway  
- Route tables  
- Public routing  

This example demonstrates my ability to design and automate AWS cloud networking using Infrastructure as Code.



















