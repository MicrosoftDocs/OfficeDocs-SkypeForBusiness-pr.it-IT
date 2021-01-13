---
title: Configurare il database delle posizioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurare, popolare e pubblicare il database delle posizioni di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 70158864446c12b2e7636a2962aced05d87c49a0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804086"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="37448-103">Configurare il database delle posizioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37448-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="37448-104">Configurare, popolare e pubblicare il database delle posizioni di E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="37448-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="37448-105">Per consentire ai client di individuare automaticamente la propria posizione in una rete, è necessario innanzitutto configurare il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="37448-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="37448-106">Per configurare il database delle posizioni, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="37448-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="37448-107">Popolare il database con il mapping degli elementi di rete ai percorsi.</span><span class="sxs-lookup"><span data-stu-id="37448-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="37448-108">Se si utilizza un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<CompanyName\> campo.</span><span class="sxs-lookup"><span data-stu-id="37448-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="37448-109">Se il database delle posizioni non viene popolato e il **percorso necessario** nei criteri percorso è impostato su **Sì** o su **dichiarazione** di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="37448-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="37448-110">Convalidare gli indirizzi in base allo stradario generale gestito dal provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="37448-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="37448-111">Pubblicare il database aggiornato.</span><span class="sxs-lookup"><span data-stu-id="37448-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="37448-112">Popolare il database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="37448-112">Populate the location database</span></span>

<span data-ttu-id="37448-113">Per individuare automaticamente i client all'interno di una rete, è necessario innanzitutto popolare il database delle posizioni con una rete wiremap, che mappa gli elementi di rete a indirizzi civici, ovvero via.</span><span class="sxs-lookup"><span data-stu-id="37448-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="37448-114">È possibile utilizzare le subnet, i punti di accesso wireless, gli interruttori e le porte per definire il wiremap.</span><span class="sxs-lookup"><span data-stu-id="37448-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="37448-115">È possibile aggiungere gli indirizzi al database delle posizioni singolarmente o in blocco utilizzando un file CSV contenente i formati di colonna descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="37448-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="37448-116">Se si utilizza un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni percorso.</span><span class="sxs-lookup"><span data-stu-id="37448-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="37448-117">È possibile includere più numeri ELIN per ogni percorso, ognuno separato da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="37448-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="37448-118">**Elemento di rete**</span><span class="sxs-lookup"><span data-stu-id="37448-118">**Network Element**</span></span>|<span data-ttu-id="37448-119">**Colonne obbligatorie**</span><span class="sxs-lookup"><span data-stu-id="37448-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="37448-120">**Punto di accesso wireless**</span><span class="sxs-lookup"><span data-stu-id="37448-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="37448-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="37448-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="37448-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="37448-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="37448-123">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="37448-123">**Subnet**</span></span> <br/> |<span data-ttu-id="37448-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="37448-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="37448-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="37448-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="37448-126">**Porta**</span><span class="sxs-lookup"><span data-stu-id="37448-126">**Port**</span></span> <br/> |<span data-ttu-id="37448-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span><span class="sxs-lookup"><span data-stu-id="37448-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="37448-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="37448-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="37448-129">**Switch**</span><span class="sxs-lookup"><span data-stu-id="37448-129">**Switch**</span></span> <br/> |<span data-ttu-id="37448-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="37448-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="37448-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="37448-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="37448-132">Per aggiungere elementi di rete al database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="37448-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="37448-133">Eseguire il cmdlet seguente per aggiungere una posizione subnet al database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="37448-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="37448-134">Per i gateway ELIN, inserire il ELIN nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="37448-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="37448-135">È possibile includere più di un ELIN.</span><span class="sxs-lookup"><span data-stu-id="37448-135">You can include more than one ELIN.</span></span> <span data-ttu-id="37448-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="37448-136">For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="37448-137">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "subnets.csv" per aggiornare in blocco le posizioni della subnet.</span><span class="sxs-lookup"><span data-stu-id="37448-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="37448-138">Eseguire il cmdlet seguente per aggiungere percorsi wireless al database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="37448-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="37448-139">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "waps.csv" per l'aggiornamento in blocco delle posizioni wireless.</span><span class="sxs-lookup"><span data-stu-id="37448-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="37448-140">Eseguire il cmdlet seguente per aggiungere le posizioni dei commutatori al database delle località.</span><span class="sxs-lookup"><span data-stu-id="37448-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="37448-141">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "switches.csv" per aggiornare in blocco le posizioni degli switch.</span><span class="sxs-lookup"><span data-stu-id="37448-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="37448-142">Eseguire il cmdlet seguente per aggiungere posizioni delle porte al database della posizione</span><span class="sxs-lookup"><span data-stu-id="37448-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="37448-143">Il valore predefinito per PortIDSubType è LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="37448-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="37448-144">È anche possibile impostarla su InterfaceAlias o su InterfaceName</span><span class="sxs-lookup"><span data-stu-id="37448-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="37448-145">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "ports.csv" per l'aggiornamento in blocco delle posizioni delle porte.</span><span class="sxs-lookup"><span data-stu-id="37448-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="37448-146">Convalidare gli indirizzi</span><span class="sxs-lookup"><span data-stu-id="37448-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="37448-147">Per convalidare gli indirizzi presenti nel database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="37448-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="37448-148">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="37448-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="37448-149">Eseguire i seguenti cmdlet per configurare la connessione del provider dei servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="37448-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="37448-150">Per convalidare gli indirizzi nel database delle posizioni, eseguire il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="37448-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="37448-151">Per convalidare indirizzi singoli, è inoltre possibile utilizzare il cmdlet **Test-CsLisCivicAddress**.</span><span class="sxs-lookup"><span data-stu-id="37448-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="37448-152">Pubblicare il database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="37448-152">Publish the location database</span></span>

<span data-ttu-id="37448-153">Le nuove posizioni aggiunte al database delle posizioni non vengono rese disponibili per il client finché non vengono pubblicate.</span><span class="sxs-lookup"><span data-stu-id="37448-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="37448-154">Se si utilizzano gateway ELIN (Emergency Location Identification Number), è necessario inoltre caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="37448-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="37448-155">Il gestore della rete PSTN può richiedere di utilizzare un formato specifico per i record ELIN.</span><span class="sxs-lookup"><span data-stu-id="37448-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="37448-156">Contattarlo per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="37448-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="37448-157">È possibile esportare i record dal database del servizio informazioni percorso e formattarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="37448-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="37448-158">Per pubblicare il database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="37448-158">To publish the location database</span></span>

-  <span data-ttu-id="37448-159">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="37448-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="37448-160">Per pubblicare il database delle posizioni, eseguire il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="37448-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


