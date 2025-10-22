# Firefly-iii

## Setup of PostgressDb

Needs to be done manually

```bash
psql -U postgres

CREATE ROLE firefly LOGIN PASSWORD 'my-secret';

CREATE DATABASE firefly;

GRANT ALL PRIVILEGES ON DATABASE firefly TO firefly;

```

### Check

```bash
\du

#                                   List of roles
# Role name |                         Attributes                         | Member of 
#-----------+------------------------------------------------------------+-----------
# firefly   |                                                            | {}
# postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}

```

### Exit

```bash
\q
```


