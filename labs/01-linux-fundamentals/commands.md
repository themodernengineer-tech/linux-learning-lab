mkdir -p ~/lfcs-lab/day1/assessment
cd ~/lfcs-lab/day1/assessment

mkdir -p configs backups logs

echo "server_name=lab01" > configs/server.conf
echo "environment=development" >> configs/server.conf

cat configs/server.conf

cp configs/server.conf backups/server.conf.bak

cmp configs/server.conf backups/server.conf.bak
echo $?

sha256sum configs/server.conf backups/server.conf.bak
