# Lab 1

#### Umsetzung der Aufgabenstellung
Über Azure wurden sowohl der Storage und auch die WebApp erstellt, welche nach der Konfiguration heruntergeladen wurden. Die beiden .json Dateien wurden danach in einem Template und einem Parameter File verbunden.

#### Parameter-file
##### Template

Die Web und Storage App werden im Abschnitt der Resourcen mithilfe der Parameter erstellt. 
Es gibt folgende Parameter und der Resourcen:

"$schema": die Adresse des .json Files an das die Version des Templates angibt

"contentVersion": gibt die Version des Dokuments an

"tags": werden verwendet um Kontrolle zu behalten, darin werden z.B. Eigentümer oder Abteilungen festgehalten

##### WebApp
Parameter:

"location": Location an der der Dienst gehostet wird.
"subscriptionId": meine subscriptionId
"name": WebApp Name
"hostingPlanName": Service Plan der App
"serverFarmResourceGroup": die Resourcen Group
"skuCode": hier Free Tier
"workerSize": VM Größe der Worker Pool Instanzen
"workerSizeId": Referenz auf Worker Pool
"numberOfWorker": Zahl der Worker
 "linuxFxVersion": Version von Linux
 
 ##### Storage
 Parameter:
 
 "locationStorage": die location an der der Service gehostet wird; hier umbenannt, weil es sonst zwei Location Parameters gibt, für die WebApp und für die StorageApp.
 "storageAccountName": der Name des Storage
 "accountType": dabei geht es um die Redundanz zum Schutz der Daten
 "kind": Art des Storages
 "accessTier": gibt an wie oft auf die Daten zugegriffen werden soll
  "minimumTlsVersion": die minimal unterstützte TLS-Version innerhalb der ARM-Vorlage
 "allowBlobPublicAccess": regelt den öffentlichen Lesezugriff
 "supportsHttpsTrafficOnly": regelt den Https Verkehr
 
 ##### Deployment
 az group deployment create 
 --name lab1
 --resource-group lab1SD
 --template-file azuredeploy.json --parameters storageName=mysdstorage

