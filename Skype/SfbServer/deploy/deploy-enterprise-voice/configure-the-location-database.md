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
ms.openlocfilehash: 5aad449d8d286fb4bd71373be33baea9cbb2c8f3
ms.sourcegitcommit: 5e6eb8286bd5eb318a901e42235e91a58946c3a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38038705"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="d54f6-103">Configurare il database della posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d54f6-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="d54f6-104">Configurare, popolare e pubblicare il database della posizione E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d54f6-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d54f6-105">Per consentire ai client di rilevare automaticamente la propria posizione all'interno di una rete, è prima di tutto necessario configurare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="d54f6-106">Per configurare il database della posizione, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d54f6-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="d54f6-107">Popolare il database con un mapping degli elementi di rete alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="d54f6-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="d54f6-108">Se si usa un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<campo\> CompanyName.</span><span class="sxs-lookup"><span data-stu-id="d54f6-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="d54f6-109">Se non si popola il database della posizione e la **posizione richiesta** nei criteri di posizione è impostata su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="d54f6-110">Convalidare gli indirizzi rispetto alla guida di indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d54f6-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="d54f6-111">Pubblicare il database aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d54f6-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="d54f6-112">Popolare il database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-112">Populate the location database</span></span>

<span data-ttu-id="d54f6-113">Per individuare automaticamente i client all'interno di una rete, è prima di tutto necessario popolare il database della posizione con una rete wiremap, che mappa gli elementi di rete agli indirizzi civici (ovvero via).</span><span class="sxs-lookup"><span data-stu-id="d54f6-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="d54f6-114">Puoi usare subnet, punti di accesso wireless, switch e porte per definire il wiremap.</span><span class="sxs-lookup"><span data-stu-id="d54f6-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="d54f6-115">È possibile aggiungere gli indirizzi al database della posizione singolarmente o in blocco usando un file CSV contenente i formati di colonna descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d54f6-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="d54f6-116">Se si usa un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="d54f6-117">È possibile includere più ELIN per ogni posizione, separate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="d54f6-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="d54f6-118">**Elemento Network**</span><span class="sxs-lookup"><span data-stu-id="d54f6-118">**Network Element**</span></span>|<span data-ttu-id="d54f6-119">**Colonne obbligatorie**</span><span class="sxs-lookup"><span data-stu-id="d54f6-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d54f6-120">**Punto di accesso wireless**</span><span class="sxs-lookup"><span data-stu-id="d54f6-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="d54f6-121">\<BSSID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<Predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="d54f6-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d54f6-122">... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\></span><span class="sxs-lookup"><span data-stu-id="d54f6-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d54f6-123">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="d54f6-123">**Subnet**</span></span> <br/> |<span data-ttu-id="d54f6-124">\<Subnet\>,\<Descrizione\>,\<posizione\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... predirezionali</span><span class="sxs-lookup"><span data-stu-id="d54f6-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d54f6-125">... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\></span><span class="sxs-lookup"><span data-stu-id="d54f6-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d54f6-126">**Porta**</span><span class="sxs-lookup"><span data-stu-id="d54f6-126">**Port**</span></span> <br/> |<span data-ttu-id="d54f6-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="d54f6-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="d54f6-128">... \<Predirectional\>,\<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<City\>,\<state\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="d54f6-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d54f6-129">**Interruttore**</span><span class="sxs-lookup"><span data-stu-id="d54f6-129">**Switch**</span></span> <br/> |<span data-ttu-id="d54f6-130">\<ChassisID\>,\<Description\>,\<location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<Predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="d54f6-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d54f6-131">... \<StreetName\>,\<StreetSuffix\>,\<Postdirectional\>,\<città\>,\<stato\>,\<Cap\>,\<paese\></span><span class="sxs-lookup"><span data-stu-id="d54f6-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="d54f6-132">Per aggiungere elementi di rete al database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="d54f6-133">Eseguire il cmdlet seguente per aggiungere una posizione subnet al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="d54f6-134">Per i gateway ELIN, inserire il nome ELIN nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="d54f6-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="d54f6-135">Puoi includere più di un ELIN.</span><span class="sxs-lookup"><span data-stu-id="d54f6-135">You can include more than one ELIN.</span></span> <span data-ttu-id="d54f6-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d54f6-136">For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="d54f6-137">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Subnets. csv" per l'aggiornamento in blocco dei percorsi della subnet.</span><span class="sxs-lookup"><span data-stu-id="d54f6-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="d54f6-138">Eseguire il cmdlet seguente per aggiungere posizioni wireless al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="d54f6-139">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "WAP. csv" per aggiornare i percorsi wireless in blocco.</span><span class="sxs-lookup"><span data-stu-id="d54f6-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="d54f6-140">Eseguire il cmdlet seguente per aggiungere posizioni di cambio al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="d54f6-141">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "switchs. csv" per le posizioni degli switch di aggiornamento in blocco.</span><span class="sxs-lookup"><span data-stu-id="d54f6-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="d54f6-142">Eseguire il cmdlet seguente per aggiungere posizioni della porta al database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="d54f6-143">Il valore predefinito per PortIDSubType è LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="d54f6-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="d54f6-144">È anche possibile impostarla su InterfaceAlias o su interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d54f6-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="d54f6-145">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Ports. csv" per l'aggiornamento in blocco delle posizioni della porta.</span><span class="sxs-lookup"><span data-stu-id="d54f6-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="d54f6-146">Convalidare gli indirizzi</span><span class="sxs-lookup"><span data-stu-id="d54f6-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="d54f6-147">Per convalidare gli indirizzi presenti nel database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="d54f6-148">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d54f6-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d54f6-149">Eseguire i cmdlet seguenti per configurare la connessione del provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d54f6-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="d54f6-150">Eseguire il cmdlet seguente per convalidare gli indirizzi nel database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="d54f6-151">Puoi anche usare il cmdlet **Test-CsLisCivicAddress** per convalidare singoli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="d54f6-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="d54f6-152">Pubblicare il database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-152">Publish the location database</span></span>

<span data-ttu-id="d54f6-153">I nuovi percorsi aggiunti al database della posizione non verranno resi disponibili al client finché non saranno stati pubblicati.</span><span class="sxs-lookup"><span data-stu-id="d54f6-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="d54f6-154">Se si usano i gateway ELIN (Emergency Location Identification Number), è anche necessario caricare i numeri ELINs nel database di identificazione automatica della posizione (ALI) del gestore della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d54f6-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="d54f6-155">Il gestore PSTN può richiedere l'uso di un formato specifico per i record ELIN.</span><span class="sxs-lookup"><span data-stu-id="d54f6-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="d54f6-156">Per informazioni dettagliate, contattare il gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="d54f6-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="d54f6-157">È possibile esportare i record dal database del servizio informazioni sulla posizione e formattarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d54f6-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="d54f6-158">Per pubblicare il database della posizione</span><span class="sxs-lookup"><span data-stu-id="d54f6-158">To publish the location database</span></span>

-  <span data-ttu-id="d54f6-159">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d54f6-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="d54f6-160">Eseguire il cmdlet seguente per pubblicare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="d54f6-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


