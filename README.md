INSTALACE APACHE
-----------------------------------
1. spust�me CLI jako administr�tor
2. cd C:\dev\apache\bin
3. spust�me p��kaz pro instalaci: httpd.exe -k install -n "Apache2.4-PhpFastCgi"
4. tento p��kaz n�m nainstaloval Windows slu�bu pojmenovanou "Apache2.4-PhpFastCgi", kter� se p�i ka�d�m spu�t�n� po��ta�e automaticky zapne

INSTALACE ApacheMonitor.exe PO SPU�T�N�
-----------------------------------
Zkop�rujeme soubor "C:\dev\apache\bin\ApacheMonitor.exe" do:
C:\Users\{u�ivatel}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
(pokud slo�ka AppData nen� vid�t, je t�eba povolit v pr�zkumn�kovi skryt� soubory)

P�ID�N� VIRTUALHOST (nov�ho projektu)
-----------------------------------
1. cd C:\dev\apache\conf\extra
2. uprav�me soubor "httpd-vhosts.conf", kam p�id�me nov� VirtualHost
3. vytvo��me slo�ku uvnit� C:\dev\www (zde je root cel�ho serveru)


ODINSTALACE APACHE
-----------------------------------
1. spust�me CLI jako administr�tor
2. cd C:\dev\apache\bin
3. spust�me p��kaz pro odinstalaci: httpd.exe -k uninstall -n "Apache2.4-PhpFastCgi"


P�EP�N�N� VERZ� PHP V CLI
-----------------------------------
Do syst�mov� prom�nn� PATH je t�eba p�idat n�sleduj�c� polo�ky:
C:\dev\bin
%PhpPath%

N�sledn� je mo�n� vyu��t p��kazy uvnit� bin/:
set-php5.6
set-php7.0
set-php7.1
set-php7.2

p��kazy je nutn� spustit jako administr�tor a n�sledn� vypnout v�echna CLI + spustit znovu jejich instance.