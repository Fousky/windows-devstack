# CO TO JE?

DevStack je lokální vývojové prostředí pro psaní PHP aplikací. Tento devstack umožňuje vyvíjet aplikace psané v různých verzích PHP na systému Windows.

# CO DEVSTACK OBSAHUJE?

- Apache 2.4
- PHP 5.6 jako FastCGI nebo CLI
- PHP 7.0 jako FastCGI nebo CLI
- PHP 7.1 jako FastCGI nebo CLI
- PHP 7.2 jako FastCGI nebo CLI
- .bat soubory, které umožňují rychlé přepínání PHP pro CLI

# LOKÁLNÍ INSTALACE DEVSTACKU

## 1. STAŽENÍ DEVSTACKU

Máme-li lokálně instalovaný GIT, naklonujeme devstack do složky C:\dev takto:

	git clone https://github.com/Fousky/windows-devstack.git C:\dev

Nebo můžeme stáhnout .ZIP archiv a ten rozbalit do složky C:\dev

## 2. INSTALACE APACHE

1. spustíme CLI jako administrátor
2. `cd C:\dev\apache\bin`
3. spustíme příkaz pro instalaci: `httpd.exe -k install -n "Apache2.4-PhpFastCgi"`
4. tento příkaz nám nainstaloval Windows službu pojmenovanou `Apache2.4-PhpFastCgi`, která se při každém spuštění počítače automaticky zapne

## 3. INSTALACE ApacheMonitor.exe PO SPUŠTĚNÍ

Zkopírujeme soubor "C:\dev\apache\bin\ApacheMonitor.exe" do:
	
	C:\Users\{uživatel}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup

(pokud složka AppData není vidět, je třeba povolit v průzkumníkovi skryté soubory)

## 4. PŘIDÁNÍ VIRTUALHOST (nového projektu)

1. `cd C:\dev\apache\conf\extra`
2. upravíme soubor `httpd-vhosts.conf`, kam přidáme nový VirtualHost
3. vytvoříme složku uvnitř `C:\dev\www` (zde je root celého serveru)

# ODINSTALACE APACHE

1. spustíme CLI jako administrátor
2. `cd C:\dev\apache\bin`
3. spustíme příkaz pro odinstalaci: `httpd.exe -k uninstall -n "Apache2.4-PhpFastCgi"`

# PŘEPÍNÁNÍ VERZÍ PHP V CLI

Do systémové proměnné PATH je třeba přidat následující položky:

- `C:\dev\bin`
- `%PhpPath%`

Následně je možné využít příkazy uvnitř bin/:

- `set-php5.6`
- `set-php7.0`
- `set-php7.1`
- `set-php7.2`

příkazy je nutné spustit jako administrátor a následně vypnout všechna CLI + spustit znovu jejich instance.
