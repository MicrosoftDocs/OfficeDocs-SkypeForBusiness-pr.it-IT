---
title: Configurare il database delle località in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Configurare, popolare e pubblicare il database delle località di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 0eb2fd8e09c09688cf8c8282b35328ca7eb1761b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597740"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurare il database delle località in Skype for Business Server
 
Configurare, popolare e pubblicare il database delle località di E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Per consentire ai client di individuare automaticamente la propria posizione in una rete, è necessario innanzitutto configurare il database delle posizioni. 
  
Per configurare il database delle località, eseguire le attività seguenti:
  
- Popolare il database con il mapping degli elementi di rete ai percorsi. Se si utilizza un gateway ELIN (Emergency Location Identification Number), è necessario includere l'ELIN nel \<CompanyName\> campo.
    
    Se non si popola il database  delle località e la posizione richiesta nei criteri percorso è impostata su **Sì** o Dichiarazione di non **responsabilità,** il client chiederà all'utente di immettere manualmente una posizione.
    
- Convalidare gli indirizzi in base allo stradario generale gestito dal provider di servizi di emergenza.
    
- Pubblicare il database aggiornato.
    
## <a name="populate-the-location-database"></a>Popolare il database delle località

Per individuare automaticamente i client all'interno di una rete, è innanzitutto necessario popolare il database delle località con una wiremap di rete, che mappa gli elementi di rete a indirizzi civici (ovvero via). Puoi usare subnet, punti di accesso wireless, commutatori e porte per definire la wiremap.
  
È possibile aggiungere indirizzi al database delle località singolarmente o in blocco utilizzando un file CSV contenente i formati di colonna descritti nella tabella seguente.
  
Se si utilizza un gateway ELIN (Emergency Location Identification Number), includere ELIN nel **campo CompanyName** per ogni posizione. È possibile includere più ELAN per ogni posizione, ognuno separato da un punto e virgola.
  
|**Elemento Network**|**Colonne obbligatorie**|
|:-----|:-----|
|**Punto di accesso wireless** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Porta** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Per aggiungere elementi di rete al database delle località

1. Eseguire il cmdlet seguente per aggiungere una posizione subnet al database delle località.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Per i gateway ELIN, inserire l'ELIN nel campo CompanyName. È possibile includere più di un ELIN. Ad esempio:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "subnets.csv" per aggiornare in blocco le posizioni delle subnet.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Eseguire il cmdlet seguente per aggiungere posizioni wireless al database delle posizioni.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "waps.csv" per aggiornare in blocco le posizioni wireless.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Eseguire il cmdlet seguente per aggiungere percorsi di commutazione al database delle posizioni.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "switches.csv" per aggiornare in blocco le posizioni del commutatore.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Eseguire il cmdlet seguente per aggiungere posizioni delle porte al database delle posizioni
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Il valore predefinito per PortIDSubType è LocallyAssigned. Puoi anche impostarlo su InterfaceAlias o InterfaceName
    
   In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "ports.csv" per aggiornare in blocco i percorsi delle porte.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Convalidare gli indirizzi

### <a name="to-validate-addresses-located-in-the-location-database"></a>Per convalidare gli indirizzi presenti nel database delle posizioni

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
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
    
## <a name="publish-the-location-database"></a>Pubblicare il database delle località

Le nuove posizioni aggiunte al database delle posizioni non vengono rese disponibili per il client finché non vengono pubblicate.
  
Se si utilizzano gateway ELIN (Emergency Location Identification Number), è necessario inoltre caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network). Il gestore della rete PSTN può richiedere di utilizzare un formato specifico per i record ELIN. Contattarlo per informazioni dettagliate. È possibile esportare i record dal database del servizio informazioni percorso e formattarli in base alle esigenze.
  
### <a name="to-publish-the-location-database"></a>Per pubblicare il database delle posizioni

-  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
- Per pubblicare il database delle posizioni, eseguire il cmdlet seguente.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


