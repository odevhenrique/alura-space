# Alura Space

Galeria de fotos do espaço desenvolvida com Django durante o curso **Django: ORM, views e buscas** da Alura.

## Sobre o projeto

O Alura Space é uma aplicação web que exibe uma galeria de imagens astronômicas gerenciadas via banco de dados. O projeto evoluiu de templates estáticos para uma aplicação completa com ORM, Django Admin personalizado e mecanismo de busca.

## Funcionalidades

- Página inicial com galeria de imagens em grid, ordenadas por data
- Página de detalhe de imagem individual
- Mecanismo de busca por nome de fotografia
- Filtro de imagens publicadas (apenas fotos marcadas como publicadas aparecem na galeria)
- Navegação lateral com categorias (Home, Mais vistas, Novas, Surpreenda-me)
- Imagem padrão "not found" para fotos sem arquivo
- Django Admin personalizado com listagem, busca, filtros e edição inline de publicação

## Tecnologias utilizadas

- Python 3.x
- Django 6.0.5
- SQLite3
- HTML5 / CSS3
- python-dotenv
- Pillow (upload e manipulação de imagens)

## O que foi praticado no curso

### Banco de dados e ORM
- Criação de `Model` com campos `CharField`, `TextField`, `ImageField`, `BooleanField` e `DateField`
- Uso do ORM Django: `objects.order_by()`, `filter()`, `get_object_or_404()`
- Geração e aplicação de migrações com `makemigrations` e `migrate`
- Campo `foto` com upload dinâmico para `fotos/%Y/%m/%d`
- Categorias com `choices` e campo `publicada` para controle de visibilidade

### Django Admin
- Registro de model com classe customizada `ModelAdmin`
- `list_display`, `list_display_links`, `search_fields`, `list_filter`, `list_editable`, `list_per_page`
- Inclusão de categorias (Nebulosa, Estrela, Galáxia, Planeta)

### Views e URLs
- View `index` filtrando apenas fotografias publicadas, ordenadas por data decrescente
- View `imagem` com parâmetro dinâmico `foto_id` na URL
- View `buscar` com leitura de parâmetro `GET` e filtro `icontains`

### Templates
- Princípio DRY com template base (`base.html`) e `{% extends %}`
- Organização com partials (`_header.html`, `_menu.html`) e `{% include %}`
- Uso de `{% url 'name' %}` para URLs nomeadas e `{% load static %}`
- Configuração de `MEDIA_URL` e `MEDIA_ROOT` para servir uploads em desenvolvimento

### Boas práticas gerais
- Variáveis de ambiente com `python-dotenv`
- Configuração de idioma (`pt-br`) e timezone
- Versionamento com Git e boas práticas de segurança em repositórios

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

# Crie um superusuário para acessar o Admin
python manage.py createsuperuser

# Inicie o servidor
python manage.py runserver
```

Acesse [http://localhost:8000](http://localhost:8000) para ver a galeria e [http://localhost:8000/admin](http://localhost:8000/admin) para gerenciar as fotografias.

## Estrutura do projeto

```
alura-space/
├── setup/                  # Configurações do projeto Django
│   ├── settings.py
│   └── urls.py
├── galeria/                # App principal
│   ├── models.py           # Model Fotografia com ORM
│   ├── admin.py            # Admin personalizado
│   ├── views.py            # index, imagem, buscar
│   ├── urls.py
│   └── migrations/
├── templates/
│   └── galeria/
│       ├── base.html           # Template base (DRY)
│       ├── index.html          # Galeria principal
│       ├── imagem.html         # Detalhe da imagem
│       ├── buscar.html         # Resultados de busca
│       └── partials/
│           ├── _header.html
│           └── _menu.html
├── setup/static/assets/
│   └── imagens/galeria/    # Imagens estáticas e not_found.jpg
├── .env                    # Variáveis de ambiente (não versionado)
├── requirements.txt
└── manage.py
```

## Cursos

- [Django: templates e boas práticas](https://www.alura.com.br) — Alura
- [Django: ORM, views e buscas](https://www.alura.com.br) — Alura
