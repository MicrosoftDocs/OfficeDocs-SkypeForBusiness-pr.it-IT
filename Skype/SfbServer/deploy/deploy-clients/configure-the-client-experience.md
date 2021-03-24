---
title: Configurare l'esperienza client con Skype for Business 2015
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
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for Business."
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096010"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="8b5b0-103">Configurare l'esperienza client con Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="8b5b0-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="8b5b0-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="8b5b0-105">Skype for Business 2015 offre una nuova esperienza utente basata sull'esperienza del prodotto skype consumer.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="8b5b0-106">Oltre a tutte le funzionalità di Lync, Skype for Business offre nuove funzionalità con controlli semplificati e icone familiari.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="8b5b0-107">Per informazioni dettagliate sulla nuova esperienza client, vedi [Esplorare Skype for Business.](https://go.microsoft.com/fwlink/?LinkId=529022)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="8b5b0-108">Skype for Business Server supporta la nuova esperienza client Skype for Business e l'esperienza client Lync.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="8b5b0-109">Gli amministratori possono scegliere l'esperienza client preferita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="8b5b0-110">Ad esempio, è possibile distribuire l'esperienza client Lync fino a quando gli utenti dell'organizzazione non sono completamente addestrati nella nuova esperienza skype for business.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="8b5b0-111">In caso contrario, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server, è consigliabile che tutti gli utenti abbiano la stessa esperienza client fino a quando tutti non vengono aggiornati al nuovo server.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b5b0-112">Se nell'organizzazione sono distribuiti sia Skype for Business Server che Lync Server, l'esperienza client predefinita varia a seconda delle versioni del server e delle impostazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="8b5b0-113">Quando gli utenti avviano Skype for Business per la prima volta, visualizzano sempre l'interfaccia utente di Skype for Business, anche se è stata selezionata l'esperienza client Lync.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="8b5b0-114">Dopo alcuni minuti, agli utenti viene richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="8b5b0-115">Per ulteriori informazioni, vedere **First launch client behavior** più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b5b0-116">L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for Business 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="8b5b0-117">Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, verificare la versione del client per assicurarsi che non inizi con il numero 16. ad esempio: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="8b5b0-118">Configurare l'esperienza client</span><span class="sxs-lookup"><span data-stu-id="8b5b0-118">Configure the client experience</span></span>

<span data-ttu-id="8b5b0-119">È possibile specificare l'esperienza client che gli utenti dell'organizzazione potranno visualizzare utilizzando il cmdlet **Set-CSClientPolicy** con il parametro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="8b5b0-120">dove XdsIdentity fa riferimento al criterio globale o a un criterio sito denominato.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="8b5b0-121">Il comando seguente seleziona l'esperienza client Skype for Business per tutti gli utenti dell'organizzazione interessati dal criterio globale (ricordare che i criteri specifici del sito o dell'utente sostituiscono i criteri globali):</span><span class="sxs-lookup"><span data-stu-id="8b5b0-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="8b5b0-122">Il comando successivo consente di selezionare l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="8b5b0-123">Il comando successivo seleziona l'esperienza client Skype for Business per tutti gli utenti all'interno del sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="8b5b0-124">Se si desidera configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente utilizzando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici utilizzando il cmdlet **Grant-CsClientPolicy.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="8b5b0-125">Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'esperienza client Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="8b5b0-126">Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto Vendite:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="8b5b0-127">Comportamenti client per il primo avvio</span><span class="sxs-lookup"><span data-stu-id="8b5b0-127">First launch client behaviors</span></span>

<span data-ttu-id="8b5b0-128">Per impostazione predefinita, quando gli utenti avviano Skype for Business 2015 per la prima volta, visualizzano sempre l'interfaccia utente di Skype for Business, anche se è stata selezionata l'esperienza client Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="8b5b0-129">Dopo alcuni minuti, agli utenti verrà chiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="8b5b0-130">Se si desidera visualizzare l'interfaccia utente di Lync quando gli utenti avviano il client Skype for Business per la prima volta, eseguire la procedura seguente prima che il client venga avviato per la prima volta dopo l'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="8b5b0-131">Verificare che il valore di sia impostato su $False nel criterio  `EnableSkypeUI` in uso come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="8b5b0-132">Aggiornare il Registro di sistema nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="8b5b0-133">È consigliabile eseguire questa operazione prima che gli utenti avviino il client Skype for Business per la prima volta e che sia necessario eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="8b5b0-134">Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer aggiunto a un dominio, vedere la sezione più avanti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="8b5b0-135">Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** crea un nuovo **valore Binary.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="8b5b0-136">Il **nome valore** deve essere **EnableSkypeUI** e i dati **valore** devono essere impostati su **00 00 00 00 00.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="8b5b0-137">La chiave dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="8b5b0-138">L'interfaccia utente di Lync verrà ora visualizzata quando gli utenti avviano il client Skype for Business per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="8b5b0-139">Controllare la visualizzazione dell'esercitazione sulla schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="8b5b0-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="8b5b0-140">Quando gli utenti aprono il client Skype for Business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include  *7 suggerimenti* rapidi che la maggior parte delle persone richiede .</span><span class="sxs-lookup"><span data-stu-id="8b5b0-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="8b5b0-141">È possibile disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="8b5b0-142">Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** crea un nuovo **valore DWORD (32 bit).**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="8b5b0-143">Il **nome del** valore deve essere **IsBasicTutorialSeenByUser** e i dati **value** devono essere impostati su **1.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="8b5b0-144">La chiave dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="8b5b0-145">Disattivare l'esercitazione sul client</span><span class="sxs-lookup"><span data-stu-id="8b5b0-145">Turn off the client tutorial</span></span>

<span data-ttu-id="8b5b0-146">Se non si desidera che gli utenti possano accedere all'esercitazione, è possibile disattivare l'esercitazione client con il valore del Registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="8b5b0-147">Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** crea un nuovo **valore DWORD (32 bit).**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="8b5b0-148">Il **nome valore** deve essere **TutorialFeatureEnabled** e i dati **value** devono essere impostati su **0.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="8b5b0-149">Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="8b5b0-150">Puoi riattivare l'esercitazione impostando i **dati valore** su **1.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="8b5b0-151">Comportamenti client predefiniti</span><span class="sxs-lookup"><span data-stu-id="8b5b0-151">Default client behaviors</span></span>

<span data-ttu-id="8b5b0-152">Se nell'organizzazione sono distribuiti sia Skype for Business Server che Lync Server, l'esperienza client varia a seconda delle versioni del server e dell'impostazione dell'interfaccia utente di Skype.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="8b5b0-153">La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="8b5b0-154">**Versione server**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-154">**Server version**</span></span>|<span data-ttu-id="8b5b0-155">**Impostazione EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="8b5b0-156">**Esperienza client**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b5b0-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b5b0-157">Skype for Business Server</span></span> |<span data-ttu-id="8b5b0-158">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="8b5b0-158">Default</span></span>  <br/> |<span data-ttu-id="8b5b0-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="8b5b0-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b5b0-160">Skype for Business Server</span></span>  |<span data-ttu-id="8b5b0-161">Vero</span><span class="sxs-lookup"><span data-stu-id="8b5b0-161">True</span></span>  <br/> |<span data-ttu-id="8b5b0-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="8b5b0-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b5b0-163">Skype for Business Server</span></span>  |<span data-ttu-id="8b5b0-164">False</span><span class="sxs-lookup"><span data-stu-id="8b5b0-164">False</span></span>  <br/> |<span data-ttu-id="8b5b0-165">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="8b5b0-166">Lync Server 2010 o Lync Server 2013 (con patch corrette)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-167">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="8b5b0-167">Default</span></span>  <br/> |<span data-ttu-id="8b5b0-168">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="8b5b0-169">Lync Server 2010 o Lync Server 2013 (con patch corrette)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-170">Vero</span><span class="sxs-lookup"><span data-stu-id="8b5b0-170">True</span></span>  <br/> |<span data-ttu-id="8b5b0-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="8b5b0-172">Lync Server 2010 o Lync Server 2013 (con patch corrette)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-173">False</span><span class="sxs-lookup"><span data-stu-id="8b5b0-173">False</span></span>  <br/> |<span data-ttu-id="8b5b0-174">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="8b5b0-175">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-176">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="8b5b0-176">Default</span></span>  <br/> |<span data-ttu-id="8b5b0-177">L'utente ha chiesto di passare alla modalità Lync (l'utente non può passare a Skype for Business in un secondo momento)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="8b5b0-178">La tabella seguente mostra l'esperienza client quando l'amministratore modifica l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="8b5b0-179">**Versione server**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-179">**Server version**</span></span>|<span data-ttu-id="8b5b0-180">**Impostazione EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="8b5b0-181">**Interfaccia utente client = Lync**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-181">**Client UI = Lync**</span></span>|<span data-ttu-id="8b5b0-182">**Interfaccia utente client = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b5b0-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b5b0-183">Skype for Business Server</span></span> |<span data-ttu-id="8b5b0-184">Vero</span><span class="sxs-lookup"><span data-stu-id="8b5b0-184">True</span></span>  <br/> |<span data-ttu-id="8b5b0-185">L'utente ha chiesto di passare a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="8b5b0-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="8b5b0-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b5b0-187">Skype for Business Server</span></span> |<span data-ttu-id="8b5b0-188">False</span><span class="sxs-lookup"><span data-stu-id="8b5b0-188">False</span></span>  <br/> |<span data-ttu-id="8b5b0-189">Modalità Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-189">Lync mode</span></span>  <br/> |<span data-ttu-id="8b5b0-190">L'utente ha chiesto di passare alla modalità Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="8b5b0-191">Lync Server 2010 o Lync Server 2013 (con patch corrette)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-192">Vero</span><span class="sxs-lookup"><span data-stu-id="8b5b0-192">True</span></span>  <br/> |<span data-ttu-id="8b5b0-193">L'utente ha chiesto di passare a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="8b5b0-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b5b0-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="8b5b0-195">Lync Server 2010 o Lync Server 2013 (con patch corrette)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-196">False</span><span class="sxs-lookup"><span data-stu-id="8b5b0-196">False</span></span>  <br/> |<span data-ttu-id="8b5b0-197">Modalità Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-197">Lync mode</span></span>  <br/> |<span data-ttu-id="8b5b0-198">L'utente ha chiesto di passare alla modalità Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="8b5b0-199">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="8b5b0-200">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="8b5b0-200">Default</span></span>  <br/> |<span data-ttu-id="8b5b0-201">Modalità Lync (non è possibile passare a Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="8b5b0-202">Modalità Lync (non è possibile passare a Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="8b5b0-203">Le versioni della patch necessarie per gestire la configurazione del client Skype for Business sono:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="8b5b0-204">Lync Server 2010 - Aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="8b5b0-205">Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="8b5b0-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="8b5b0-206">Lync Server 2013 - Aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="8b5b0-207">Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="8b5b0-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="8b5b0-208">Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer aggiunto a un dominio</span><span class="sxs-lookup"><span data-stu-id="8b5b0-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="8b5b0-209">L'aggiornamento del Registro di sistema per visualizzare l'esperienza del client Lync la prima volta che un utente avvia il client Skype for Business 2015 deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="8b5b0-210">Se si utilizza un oggetto Criteri di gruppo per aggiornare il Registro di sistema, è necessario definire l'oggetto per creare un nuovo valore anziché aggiornare i dati value.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="8b5b0-211">Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposta i dati valore su 0.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="8b5b0-212">La procedura seguente descrive come modificare il Registro di sistema in modo che l'esperienza client Lync sia visualizzata la prima volta che un utente avvia il client Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="8b5b0-213">È inoltre possibile utilizzare questa procedura per aggiornare il Registro di sistema per disabilitare l'esercitazione sulla schermata iniziale come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="8b5b0-214">Per creare l'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="8b5b0-214">To create the GPO</span></span>

1. <span data-ttu-id="8b5b0-215">Avviare la **console Gestione Criteri di gruppo.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="8b5b0-216">Per informazioni su come utilizzare Console Gestione Criteri di gruppo, vedere [Console Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8b5b0-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="8b5b0-217">Fare clic con il pulsante destro **del mouse** sul nodo Oggetti Criteri di gruppo e **scegliere Nuovo** dal menu.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="8b5b0-218">Nella finestra **di dialogo Nuovo oggetto** Criteri di gruppo immettere un nome per l'oggetto Criteri di gruppo, ad esempio MakeLyncDefaultUI, e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="8b5b0-219">Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo appena creato e scegli **Modifica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="8b5b0-220">**Nell'Editor Gestione Criteri di gruppo** espandere Configurazione **utente,** **Preferenze,** Impostazioni **di Windows** e quindi selezionare il nodo Registro **di** sistema.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="8b5b0-221">Fare clic con il pulsante **destro** del mouse sul nodo Registro di sistema e quindi scegliere **Nuovo elemento** del Registro  >  **di sistema**.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="8b5b0-222">Nella finestra **di dialogo Nuove proprietà del Registro** di sistema aggiornare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="8b5b0-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-223">**Field**</span></span>|<span data-ttu-id="8b5b0-224">**Valore da selezionare o immettere**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8b5b0-225">**Azione**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-225">**Action**</span></span> <br/> |<span data-ttu-id="8b5b0-226">**Creare**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="8b5b0-227">**Hive**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-227">**Hive**</span></span> <br/> | <span data-ttu-id="8b5b0-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="8b5b0-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="8b5b0-229">**Percorso chiave**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-229">**Key Path**</span></span> <br/> |<span data-ttu-id="8b5b0-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="8b5b0-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="8b5b0-231">**Nome valore**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-231">**Value name**</span></span> <br/> |<span data-ttu-id="8b5b0-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="8b5b0-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="8b5b0-233">**Tipo valore**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-233">**Value type**</span></span> <br/> |<span data-ttu-id="8b5b0-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="8b5b0-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="8b5b0-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-235">**Value data**</span></span> <br/> |<span data-ttu-id="8b5b0-236">00000000</span><span class="sxs-lookup"><span data-stu-id="8b5b0-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="8b5b0-237">Fare **clic su OK** per salvare le modifiche e quindi chiudere l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="8b5b0-238">Sarà quindi necessario collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui si desidera assegnare il criterio, ad esempio un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="8b5b0-239">Per utilizzare l'oggetto Criteri di gruppo per assegnare il criterio</span><span class="sxs-lookup"><span data-stu-id="8b5b0-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="8b5b0-240">Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sull'unità organizzativa a cui si desidera assegnare il criterio e quindi scegliere Collega a un oggetto Criteri **di gruppo esistente.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="8b5b0-241">Nella finestra **di dialogo Seleziona oggetto** Criteri di gruppo selezionare l'oggetto Criteri di gruppo creato e quindi scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="8b5b0-242">Nel computer dell'utente di destinazione, aprire un prompt dei comandi e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="8b5b0-243">Al prompt dei comandi, digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8b5b0-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="8b5b0-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="8b5b0-245">Di seguito viene visualizzato "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="8b5b0-246">È inoltre possibile verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="8b5b0-247">Aprire l'editor del Registro di sistema e passare alla **chiave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].**</span><span class="sxs-lookup"><span data-stu-id="8b5b0-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="8b5b0-248">Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, verrà visualizzato un valore denominato EnableSkypeUI con un valore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="8b5b0-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
