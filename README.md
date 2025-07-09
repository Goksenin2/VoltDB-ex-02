# VoltDB-ex-02

A quick guide to deploy VoltDB CE in Docker on a Google Cloud VM and run simple SQL.

## Prerequisites
- GCP Compute Engine VM (Ubuntu or Debian)
- SSH access & Docker installed on the VM

## Quick Steps

1. SSH into your VM

2. Install Docker (if needed)

3. Deploy VoltDB container  

4. Interactive SQL shell  

5. Batch-mode script  
```bash
cat <<EOF > setup.sql
DROP TABLE person;
CREATE TABLE person (id INTEGER, name VARCHAR);
INSERT INTO person VALUES (1, 'Ecem');
SELECT * FROM person;
EOF

docker exec -i node1 /usr/local/opt/voltdb/6.4/bin/sqlcmd < setup.sql


