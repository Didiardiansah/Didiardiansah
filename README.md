- 👋 Hi, I’m @Didiardiansah
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Didiardiansah/Didiardiansah is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
Sorry lupa share yang ini.

snap=$(curl -s http://94.250.203.6:90 | egrep -o ">ollo-snap*.*tar" | tr -d ">")
sudo systemctl stop ollod.service
rm-rf  $HOME/.ollo/data
wget -P $HOME http://94.250.203.6:90/${snap}
tar xf $HOME/${snap} -C $HOME/.ollo
rm $HOME/${snap}
wget -q -O $HOME/.ollo/config/addrbook.json http://94.250.203.6:90/ollo-addrbook.json
sudo systemctl restart ollod.service
journalctl -u ollod.service -f -o cat
