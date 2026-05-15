# Alura Space

Galeria de fotos do espaço desenvolvida com Django durante o curso **Django: templates e boas práticas** da Alura.

## Sobre o projeto

O Alura Space é uma aplicação web que exibe uma galeria de imagens astronômicas. O projeto foi desenvolvido com foco em aprender os fundamentos do Django, desde a configuração do ambiente até boas práticas com templates.

## Funcionalidades

- Página inicial com galeria de imagens em grid
- Página de detalhe de imagem individual
- Navegação lateral com categorias (Home, Mais vistas, Novas, Surpreenda-me)
- Barra de busca no cabeçalho
- Layout responsivo com design espacial

## Tecnologias utilizadas

- Python 3.x
- Django 6.0.5
- SQLite3
- HTML5 / CSS3
- python-dotenv

## O que foi praticado no curso

- Criação e configuração de um projeto Django com `virtualenv`
- Configuração de idioma (`pt-br`) e timezone
- Uso de variáveis de ambiente com `python-dotenv` para proteger dados sensíveis
- Versionamento com Git e GitHub, incluindo boas práticas de segurança em repositórios
- Estrutura de projeto e app no Django
- Criação de views e configuração de URLs (projeto e app)
- Isolamento de URLs por app com `include()`
- Carregamento de templates e arquivos estáticos (`{% load static %}`)
- Uso de `{% url 'name' %}` para URLs nomeadas
- Princípio DRY com template base (`base.html`) e `{% extends %}`
- Organização com partials e `{% include %}`

## Como executar

**Pré-requisitos:** Python 3.x instalado.

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/alura-space.git
cd alura-space

# Crie e ative o ambiente virtual
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # Linux/macOS

# Instale as dependências
pip install -r requirements.txt

# Crie o arquivo .env na raiz do projeto
echo SECRET_KEY=sua-chave-secreta-aqui > .env

# Execute as migrações
python manage.py migrate

# Inicie o servidor
python manage.py runserver
```

Acesse [http://localhost:8000](http://localhost:8000) no navegador.

## Estrutura do projeto

```
alura-space/
├── setup/              # Configurações do projeto Django
│   ├── settings.py
│   └── urls.py
├── galeria/            # App principal
│   ├── views.py
│   └── urls.py
├── templates/
│   └── galeria/
│       ├── base.html       # Template base (DRY)
│       ├── index.html      # Página da galeria
│       ├── imagem.html     # Detalhe da imagem
│       └── partials/
│           └── _footer.html
├── static/
│   ├── styles/style.css
│   └── assets/
├── .env                # Variáveis de ambiente (não versionado)
├── requirements.txt
└── manage.py
```

## Curso

[Django: templates e boas práticas](https://www.alura.com.br) — Alura
