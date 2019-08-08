---
title: Configurare il database della posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurare, popolare e pubblicare il database della posizione E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 36ddd57e39b51171581c0c6316f165f44879e3f9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233892"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurare il database della posizione in Skype for Business Server
 
Configurare, popolare e pubblicare il database della posizione E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Per consentire ai client di rilevare automaticamente la propria posizione all'interno di una rete, è prima di tutto necessario configurare il database della posizione. 
  
Per configurare il database della posizione, eseguire le attività seguenti:
  
- Popolare il database con un mapping degli elementi di rete alle posizioni. Se si usa un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<campo\> CompanyName.
    
    Se non si popola il database della posizione e la **posizione richiesta** nei criteri di posizione è impostata su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.
    
- Convalidare gli indirizzi rispetto alla guida di indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1.
    
- Pubblicare il database aggiornato.
    
## <a name="populate-the-location-database"></a>Popolare il database della posizione

Per individuare automaticamente i client all'interno di una rete, è prima di tutto necessario popolare il database della posizione con una rete wiremap, che mappa gli elementi di rete agli indirizzi civici (ovvero via). Puoi usare subnet, punti di accesso wireless, switch e porte per definire il wiremap.
  
È possibile aggiungere gli indirizzi al database della posizione singolarmente o in blocco usando un file CSV contenente i formati di colonna descritti nella tabella seguente.
  
Se si usa un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni posizione. È possibile includere più ELIN per ogni posizione, separate da un punto e virgola.
  
|**Elemento Network**|**Colonne obbligatorie**|
|:-----|:-----|
|**Punto di accesso wireless** <br/> |\<BSSID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<Predirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Descrizione\>,\<posizione\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... predirezionali  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\>  <br/> |
|**Porta** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\< ,...\>HouseNumberSuffix  <br/> ... \<Predirectional\>,\<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<City\>,\<state\>,\<PostalCode\>,\< Paese\>  <br/> |
|**Interruttore** <br/> |\<ChassisID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<Predirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Per aggiungere elementi di rete al database della posizione

1. Eseguire il cmdlet seguente per aggiungere una posizione subnet al database della posizione.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Per i gateway ELIN, inserire il nome ELIN nel campo CompanyName. Puoi includere più di un ELIN. Ad esempio:
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Subnets. csv" per l'aggiornamento in blocco dei percorsi della subnet.
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Eseguire il cmdlet seguente per aggiungere posizioni wireless al database della posizione.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "WAP. csv" per aggiornare i percorsi wireless in blocco.
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Eseguire il cmdlet seguente per aggiungere posizioni di cambio al database della posizione.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "switchs. csv" per le posizioni degli switch di aggiornamento in blocco.
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Eseguire il cmdlet seguente per aggiungere posizioni della porta al database della posizione
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Il valore predefinito per PortIDSubType è LocallyAssigned. È anche possibile impostarla su InterfaceAlias o su interfaccia utente
    
   In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Ports. csv" per l'aggiornamento in blocco delle posizioni della porta.
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Convalidare gli indirizzi

### <a name="to-validate-addresses-located-in-the-location-database"></a>Per convalidare gli indirizzi presenti nel database della posizione

1.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire i cmdlet seguenti per configurare la connessione del provider di servizi di emergenza.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Eseguire il cmdlet seguente per convalidare gli indirizzi nel database della posizione.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Puoi anche usare il cmdlet **Test-CsLisCivicAddress** per convalidare singoli indirizzi.
    
## <a name="publish-the-location-database"></a>Pubblicare il database della posizione

I nuovi percorsi aggiunti al database della posizione non verranno resi disponibili al client finché non saranno stati pubblicati.
  
Se si usano i gateway ELIN (Emergency Location Identification Number), è anche necessario caricare i numeri ELINs nel database di identificazione automatica della posizione (ALI) del gestore della rete PSTN (Public Switched Telephone Network). Il gestore PSTN può richiedere l'uso di un formato specifico per i record ELIN. Per informazioni dettagliate, contattare il gestore PSTN. È possibile esportare i record dal database del servizio informazioni sulla posizione e formattarli in base alle esigenze.
  
### <a name="to-publish-the-location-database"></a>Per pubblicare il database della posizione

-  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
- Eseguire il cmdlet seguente per pubblicare il database della posizione.
    
  ```
  Publish-CsLisConfiguration
  ```


