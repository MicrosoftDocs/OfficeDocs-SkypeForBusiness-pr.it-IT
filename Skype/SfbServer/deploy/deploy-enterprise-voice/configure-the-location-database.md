---
title: Configurare il database del percorso in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurare, popolare e pubblicare il database del percorso E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: fc7f53e1b62ec23e8075a9eac0d1158ee0143a5b
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671562"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurare il database del percorso in Skype for Business Server
 
Configurare, popolare e pubblicare il database del percorso E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Per consentire ai client di individuare automaticamente la propria posizione in una rete, è necessario innanzitutto configurare il database delle posizioni. 
  
Per configurare il database della posizione, eseguire le attività seguenti:
  
- Popolare il database con il mapping degli elementi di rete ai percorsi. Se si usa un gateway ELIN (Emergency Location Identification Number), è necessario includere L'ELIN nel \<CompanyName\> campo .
    
    Se non si popola il database della posizione e la **posizione richiesta** nei criteri di posizione è impostata su **Sì** o **Non responsabilità**, il client richiederà all'utente di immettere manualmente una posizione.
    
- Convalidare gli indirizzi in base allo stradario generale gestito dal provider di servizi di emergenza.
    
- Pubblicare il database aggiornato.
    
## <a name="populate-the-location-database"></a>Popolare il database della posizione

Per individuare automaticamente i client all'interno di una rete, è prima necessario popolare il database della posizione con una mappa di rete, che esegue il mapping degli elementi di rete agli indirizzi civici (ovvero strada). È possibile usare subnet, punti di accesso wireless, commutatori e porte per definire la mappa di rete.
  
È possibile aggiungere indirizzi al database dei percorsi singolarmente o in blocco usando un file CSV che contiene i formati di colonna descritti nella tabella seguente.
  
Se si usa un gateway ELIN (Emergency Location Identification Number), includere ELIN nel campo **CompanyName** per ogni posizione. È possibile includere più ELIN per ogni posizione, ognuna separata da un punto e virgola.
  
|**Elemento Network**|**Colonne obbligatorie**|
|:-----|:-----|
|**Punto di accesso wireless** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ...\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Per aggiungere elementi di rete al database del percorso

1. Eseguire il cmdlet seguente per aggiungere un percorso di subnet al database della posizione.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Per i gateway ELIN, inserire ELIN nel campo CompanyName. È possibile includere più di un ELIN. Ad esempio:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "subnets.csv" per aggiornare in blocco i percorsi delle subnet.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Eseguire il cmdlet seguente per aggiungere percorsi wireless al database della posizione.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "waps.csv" per aggiornare in blocco i percorsi wireless.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Eseguire il cmdlet seguente per aggiungere percorsi di commutazione al database della posizione.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "switches.csv" per aggiornare in blocco i percorsi dei commutatori.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Eseguire il cmdlet seguente per aggiungere i percorsi delle porte al database dei percorsi
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Il valore predefinito per PortIDSubType è LocalAssigned. È anche possibile impostarlo su InterfaceAlias o InterfaceName
    
   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "ports.csv" per aggiornare in blocco i percorsi delle porte.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Convalidare gli indirizzi

### <a name="to-validate-addresses-located-in-the-location-database"></a>Per convalidare gli indirizzi presenti nel database delle posizioni

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire i seguenti cmdlet per configurare la connessione del provider dei servizi di emergenza.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Per convalidare gli indirizzi nel database delle posizioni, eseguire il cmdlet seguente.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Per convalidare indirizzi singoli, è inoltre possibile utilizzare il cmdlet **Test-CsLisCivicAddress**.
    
## <a name="publish-the-location-database"></a>Pubblicare il database del percorso

Le nuove posizioni aggiunte al database delle posizioni non vengono rese disponibili per il client finché non vengono pubblicate.
  
Se si utilizzano gateway ELIN (Emergency Location Identification Number), è necessario inoltre caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network). Il gestore della rete PSTN può richiedere di utilizzare un formato specifico per i record ELIN. Contattarlo per informazioni dettagliate. È possibile esportare i record dal database del servizio Location Information e formattarli in base alle esigenze.
  
### <a name="to-publish-the-location-database"></a>Per pubblicare il database delle posizioni

-  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
- Per pubblicare il database delle posizioni, eseguire il cmdlet seguente.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


