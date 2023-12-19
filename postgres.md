### Basic

```bash
psql -U postgres

postgres --version

sudo systemctl status postgresql
sudo systemctl start postgresql
```

### Upgrade

```bash
# stop postgres
sudo systemctl stop postgresql
sudo systemctl status postgresql

# backup old cluster
sudo mv /var/lib/postgres/data /var/lib/postgres/data_backup

# initialize new cluster
sudo mkdir /var/lib/postgres/data /var/lib/postgres/tmp
sudo chown postgres:postgres /var/lib/postgres/data /var/lib/postgres/tmp

sudo su - postgres
cd /var/lib/postgres/tmp
initdb -D /var/lib/postgres/data --locale=C.UTF-8 --encoding=UTF8 --data-checksums

# (incoplete)
# https://wiki.archlinux.org/title/PostgreSQL#Upgrading_PostgreSQL
```

### New

```bash
createuser --interactive

sudo su - postgres
initdb --locale en_US.UTF-8 -D /var/lib/postgres/data
exit
```
