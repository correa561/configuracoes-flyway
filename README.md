📦 Flyway - Migrações de Banco de Dados

Este projeto utiliza o Flyway para gerenciar versões do esquema de banco de dados de forma automática.

✅ Configuração do Flyway

As configurações do Flyway estão definidas no arquivo application.properties (ou application.yml, dependendo do seu projeto Spring Boot):

# Ativa o Flyway
spring.flyway.enabled=true
# Caminho onde estão os scripts de migração
spring.flyway.locations=classpath:db/migrations
# Permite aplicar as migrações mesmo se o banco já existir
spring.flyway.baseline-on-migrate=true

🔍 Explicando as Propriedades
| Propriedade                              | Descrição                                                                                             |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `spring.flyway.enabled=true`             | Habilita o Flyway para rodar as migrações automaticamente na inicialização da aplicação.              |
| `spring.flyway.locations=...`            | Define o caminho onde os scripts `.sql` de migração estão localizados. Ex: `resources/db/migrations`. |
| `spring.flyway.baseline-on-migrate=true` | Cria uma baseline (marco inicial) se o banco já contiver dados, evitando erros em bancos existentes.  |

📁 Estrutura Esperada

Se estiver usando a configuração acima, crie seus scripts SQL no seguinte caminho:

src/
└── main/
    └── resources/
        └── db/
            └── migrations/
                ├── V1__criar_tabela_usuario.sql
                ├── V2__adicionar_coluna_email.sql
                └── ...



⚠️ Lembre-se: os nomes dos arquivos devem seguir o padrão V<versão>__<descricao>.sql para que o Flyway os reconheça corretamente.
