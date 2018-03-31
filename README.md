INSTALACE APACHE
-----------------------------------
1. spustíme CLI jako administrátor
2. cd C:\dev\apache\bin
3. spustíme pøíkaz pro instalaci: httpd.exe -k install -n "Apache2.4-PhpFastCgi"
4. tento pøíkaz nám nainstaloval Windows službu pojmenovanou "Apache2.4-PhpFastCgi", která se pøi každém spuštìní poèítaèe automaticky zapne

INSTALACE ApacheMonitor.exe PO SPUŠTÌNÍ
-----------------------------------
Zkopírujeme soubor "C:\dev\apache\bin\ApacheMonitor.exe" do:
C:\Users\{uživatel}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
(pokud složka AppData není vidìt, je tøeba povolit v prùzkumníkovi skryté soubory)

PØIDÁNÍ VIRTUALHOST (nového projektu)
-----------------------------------
1. cd C:\dev\apache\conf\extra
2. upravíme soubor "httpd-vhosts.conf", kam pøidáme nový VirtualHost
3. vytvoøíme složku uvnitø C:\dev\www (zde je root celého serveru)


ODINSTALACE APACHE
-----------------------------------
1. spustíme CLI jako administrátor
2. cd C:\dev\apache\bin
3. spustíme pøíkaz pro odinstalaci: httpd.exe -k uninstall -n "Apache2.4-PhpFastCgi"


PØEPÍNÁNÍ VERZÍ PHP V CLI
-----------------------------------
Do systémové promìnné PATH je tøeba pøidat následující položky:
C:\dev\bin
%PhpPath%

Následnì je možné využít pøíkazy uvnitø bin/:
set-php5.6
set-php7.0
set-php7.1
set-php7.2

pøíkazy je nutné spustit jako administrátor a následnì vypnout všechna CLI + spustit znovu jejich instance.