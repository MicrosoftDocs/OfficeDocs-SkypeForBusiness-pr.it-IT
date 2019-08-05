---
title: Configurare l'esperienza client con Skype for business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business."
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195002"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="86e1b-103">Configurare l'esperienza client con Skype for business 2015</span><span class="sxs-lookup"><span data-stu-id="86e1b-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="86e1b-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business 2015.</span><span class="sxs-lookup"><span data-stu-id="86e1b-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="86e1b-105">Skype for business 2015 offre una nuova esperienza utente basata sull'esperienza di prodotto consumer Skype.</span><span class="sxs-lookup"><span data-stu-id="86e1b-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="86e1b-106">Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note.</span><span class="sxs-lookup"><span data-stu-id="86e1b-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="86e1b-107">Per informazioni dettagliate sulla nuova esperienza client, vedere [esplorare Skype for business](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="86e1b-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="86e1b-108">Skype for Business Server supporta la nuova esperienza client Skype for business e l'esperienza client Lync.</span><span class="sxs-lookup"><span data-stu-id="86e1b-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="86e1b-109">Come amministratore, puoi scegliere l'esperienza client preferita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="86e1b-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="86e1b-110">Ad esempio, potresti voler distribuire l'esperienza del client Lync fino a quando gli utenti dell'organizzazione non saranno completamente formati nella nuova esperienza di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="86e1b-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="86e1b-111">In alternativa, se non hai ancora aggiornato tutti gli utenti a Skype for Business Server, potresti volere che tutti gli utenti abbiano la stessa esperienza client finché tutti non vengono aggiornati nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="86e1b-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86e1b-112">Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza client predefinita sarà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="86e1b-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="86e1b-113">Quando gli utenti lanciano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se hai selezionato l'esperienza del client Lync.</span><span class="sxs-lookup"><span data-stu-id="86e1b-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="86e1b-114">Dopo alcuni minuti, agli utenti viene chiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="86e1b-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="86e1b-115">Per altre informazioni, vedere **prima** di tutto avviare il comportamento del client più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="86e1b-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86e1b-116">L'esperienza client di Lync 2013 non è un'opzione per le versioni client Skype for business 2016 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="86e1b-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="86e1b-117">Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="86e1b-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="86e1b-118">Configurare l'esperienza client</span><span class="sxs-lookup"><span data-stu-id="86e1b-118">Configure the client experience</span></span>

<span data-ttu-id="86e1b-119">Puoi specificare l'esperienza client che gli utenti dell'organizzazione vedranno usando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="86e1b-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="86e1b-120">dove XdsIdentity si riferisce al criterio globale o a un criterio del sito denominato.</span><span class="sxs-lookup"><span data-stu-id="86e1b-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="86e1b-121">Il comando seguente seleziona l'esperienza del client Skype for business per tutti gli utenti dell'organizzazione interessati dal criterio globale (Ricordati che i criteri per il sito o i criteri specifici dell'utente sostituiscono il criterio globale):</span><span class="sxs-lookup"><span data-stu-id="86e1b-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="86e1b-122">Il comando successivo seleziona l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:</span><span class="sxs-lookup"><span data-stu-id="86e1b-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="86e1b-123">Il comando successivo seleziona l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="86e1b-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="86e1b-124">Se si vuole configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente usando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici tramite **Grant-CsClientPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86e1b-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="86e1b-125">Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'esperienza del client Skype for business:</span><span class="sxs-lookup"><span data-stu-id="86e1b-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="86e1b-126">Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto vendite:</span><span class="sxs-lookup"><span data-stu-id="86e1b-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="86e1b-127">Comportamenti del client al primo avvio</span><span class="sxs-lookup"><span data-stu-id="86e1b-127">First launch client behaviors</span></span>

<span data-ttu-id="86e1b-128">Per impostazione predefinita, quando gli utenti avviano Skype for business 2015 per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto precedentemente.</span><span class="sxs-lookup"><span data-stu-id="86e1b-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="86e1b-129">Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="86e1b-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="86e1b-130">Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="86e1b-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="86e1b-131">Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio in uso come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="86e1b-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="86e1b-p106">Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="86e1b-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="86e1b-135">Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** creare un nuovo valore **binario** .</span><span class="sxs-lookup"><span data-stu-id="86e1b-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="86e1b-136">**Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="86e1b-137">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86e1b-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="86e1b-138">L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="86e1b-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="86e1b-139">Controllare la visualizzazione dell'esercitazione nella schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="86e1b-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="86e1b-140">Quando gli utenti aprono il client Skype for business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include *7 suggerimenti veloci che la maggior parte delle persone richiede*.</span><span class="sxs-lookup"><span data-stu-id="86e1b-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="86e1b-141">Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:</span><span class="sxs-lookup"><span data-stu-id="86e1b-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="86e1b-142">Nella chiave **[HKEY_CURRENT_USER\software\microsoft\office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="86e1b-143">**Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="86e1b-144">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86e1b-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="86e1b-145">Disattivare l'esercitazione nel client</span><span class="sxs-lookup"><span data-stu-id="86e1b-145">Turn off the client tutorial</span></span>

<span data-ttu-id="86e1b-146">Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="86e1b-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="86e1b-147">Nella chiave **[HKEY_CURRENT_USER\software\microsoft\office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="86e1b-148">**Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="86e1b-149">Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="86e1b-150">Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="86e1b-151">Comportamenti client predefiniti</span><span class="sxs-lookup"><span data-stu-id="86e1b-151">Default client behaviors</span></span>

<span data-ttu-id="86e1b-152">Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza del client sarà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente Skype.</span><span class="sxs-lookup"><span data-stu-id="86e1b-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="86e1b-153">La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="86e1b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="86e1b-154">**Versione del server**</span><span class="sxs-lookup"><span data-stu-id="86e1b-154">**Server version**</span></span>|<span data-ttu-id="86e1b-155">**Impostazione EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="86e1b-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="86e1b-156">**Esperienza client**</span><span class="sxs-lookup"><span data-stu-id="86e1b-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86e1b-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86e1b-157">Skype for Business Server</span></span> |<span data-ttu-id="86e1b-158">Predefinita</span><span class="sxs-lookup"><span data-stu-id="86e1b-158">Default</span></span>  <br/> |<span data-ttu-id="86e1b-159">Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="86e1b-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86e1b-160">Skype for Business Server</span></span>  |<span data-ttu-id="86e1b-161">True</span><span class="sxs-lookup"><span data-stu-id="86e1b-161">True</span></span>  <br/> |<span data-ttu-id="86e1b-162">Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="86e1b-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86e1b-163">Skype for Business Server</span></span>  |<span data-ttu-id="86e1b-164">False</span><span class="sxs-lookup"><span data-stu-id="86e1b-164">False</span></span>  <br/> |<span data-ttu-id="86e1b-165">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="86e1b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="86e1b-166">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="86e1b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="86e1b-167">Predefinita</span><span class="sxs-lookup"><span data-stu-id="86e1b-167">Default</span></span>  <br/> |<span data-ttu-id="86e1b-168">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="86e1b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="86e1b-169">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="86e1b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="86e1b-170">True</span><span class="sxs-lookup"><span data-stu-id="86e1b-170">True</span></span>  <br/> |<span data-ttu-id="86e1b-171">Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="86e1b-172">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="86e1b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="86e1b-173">False</span><span class="sxs-lookup"><span data-stu-id="86e1b-173">False</span></span>  <br/> |<span data-ttu-id="86e1b-174">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="86e1b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="86e1b-175">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="86e1b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="86e1b-176">Predefinita</span><span class="sxs-lookup"><span data-stu-id="86e1b-176">Default</span></span>  <br/> |<span data-ttu-id="86e1b-177">L'utente ha chiesto di passare alla modalità Lync (l'utente non può passare a Skype for business in seguito)</span><span class="sxs-lookup"><span data-stu-id="86e1b-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="86e1b-178">La tabella seguente mostra l'esperienza del client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:</span><span class="sxs-lookup"><span data-stu-id="86e1b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="86e1b-179">**Versione del server**</span><span class="sxs-lookup"><span data-stu-id="86e1b-179">**Server version**</span></span>|<span data-ttu-id="86e1b-180">**Impostazione EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="86e1b-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="86e1b-181">**Interfaccia utente client = Lync**</span><span class="sxs-lookup"><span data-stu-id="86e1b-181">**Client UI = Lync**</span></span>|<span data-ttu-id="86e1b-182">**Interfaccia utente client = Skype for business**</span><span class="sxs-lookup"><span data-stu-id="86e1b-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="86e1b-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86e1b-183">Skype for Business Server</span></span> |<span data-ttu-id="86e1b-184">True</span><span class="sxs-lookup"><span data-stu-id="86e1b-184">True</span></span>  <br/> |<span data-ttu-id="86e1b-185">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="86e1b-186">Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="86e1b-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86e1b-187">Skype for Business Server</span></span> |<span data-ttu-id="86e1b-188">False</span><span class="sxs-lookup"><span data-stu-id="86e1b-188">False</span></span>  <br/> |<span data-ttu-id="86e1b-189">Modalità Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-189">Lync mode</span></span>  <br/> |<span data-ttu-id="86e1b-190">L'utente ha chiesto di passare alla modalità Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="86e1b-191">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="86e1b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="86e1b-192">True</span><span class="sxs-lookup"><span data-stu-id="86e1b-192">True</span></span>  <br/> |<span data-ttu-id="86e1b-193">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="86e1b-194">Skype for business</span><span class="sxs-lookup"><span data-stu-id="86e1b-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="86e1b-195">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="86e1b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="86e1b-196">False</span><span class="sxs-lookup"><span data-stu-id="86e1b-196">False</span></span>  <br/> |<span data-ttu-id="86e1b-197">Modalità Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-197">Lync mode</span></span>  <br/> |<span data-ttu-id="86e1b-198">L'utente ha chiesto di passare alla modalità Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="86e1b-199">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="86e1b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="86e1b-200">Predefinita</span><span class="sxs-lookup"><span data-stu-id="86e1b-200">Default</span></span>  <br/> |<span data-ttu-id="86e1b-201">Modalità Lync (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="86e1b-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="86e1b-202">Modalità Lync (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="86e1b-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="86e1b-203">Le versioni di patch necessarie per gestire la configurazione del client Skype for business sono:</span><span class="sxs-lookup"><span data-stu-id="86e1b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="86e1b-204">Lync Server 2010-aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="86e1b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="86e1b-205">Per informazioni, vedere [aggiornamenti per Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="86e1b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="86e1b-206">Lync Server 2013-aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86e1b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="86e1b-207">Per informazioni, vedere [aggiornamenti per Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="86e1b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="86e1b-208">Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio</span><span class="sxs-lookup"><span data-stu-id="86e1b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="86e1b-209">L'aggiornamento del registro di sistema per visualizzare l'esperienza del client Lync la prima volta che un utente avvia il client Skype for business 2015 deve essere eseguita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="86e1b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="86e1b-210">Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore.</span><span class="sxs-lookup"><span data-stu-id="86e1b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="86e1b-211">Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0.</span><span class="sxs-lookup"><span data-stu-id="86e1b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="86e1b-212">La procedura seguente descrive come modificare il registro di sistema in modo che l'esperienza del client Lync venga visualizzata la prima volta che un utente avvia il client Skype for business 2015.</span><span class="sxs-lookup"><span data-stu-id="86e1b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="86e1b-213">Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="86e1b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="86e1b-214">Per creare l'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="86e1b-214">To create the GPO</span></span>

1. <span data-ttu-id="86e1b-215">Avvia la **Console Gestione Criteri di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="86e1b-216">Per informazioni su come usare la Console Gestione Criteri di gruppo, vedi [Console Gestione Criteri di gruppo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="86e1b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="86e1b-217">Fai clic con il pulsante destro del mouse sul nodo **Oggetti Criteri di gruppo** e seleziona **Nuovo** nel menu.</span><span class="sxs-lookup"><span data-stu-id="86e1b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="86e1b-218">Nella finestra di dialogo **Nuovo oggetto Criteri di gruppo** immetti un nome per l'oggetto Criteri di gruppo, ad esempioMakeLyncDefaultUI, quindi fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="86e1b-219">Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo creato, quindi seleziona **Modifica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="86e1b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="86e1b-220">Nella finestra **Editor Gestione Criteri di gruppo** espandi **Configurazione utente**, espandi **Preferenze**, quindi **Impostazioni di Windows** e seleziona il nodo **Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="86e1b-221">Fai clic con il pulsante destro del mouse sul nodo **Registro di sistema**, quindi seleziona **Nuovo** > **Elemento Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="86e1b-222">Nella finestra di dialogo **Nuove proprietà Registro di sistema** aggiorna i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="86e1b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="86e1b-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="86e1b-223">**Field**</span></span>|<span data-ttu-id="86e1b-224">**Valore da selezionare o immettere**</span><span class="sxs-lookup"><span data-stu-id="86e1b-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="86e1b-225">**Azione**</span><span class="sxs-lookup"><span data-stu-id="86e1b-225">**Action**</span></span> <br/> |<span data-ttu-id="86e1b-226">**Create**</span><span class="sxs-lookup"><span data-stu-id="86e1b-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="86e1b-227">**Hive**</span><span class="sxs-lookup"><span data-stu-id="86e1b-227">**Hive**</span></span> <br/> | <span data-ttu-id="86e1b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="86e1b-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="86e1b-229">**Percorso chiave**</span><span class="sxs-lookup"><span data-stu-id="86e1b-229">**Key Path**</span></span> <br/> |<span data-ttu-id="86e1b-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="86e1b-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="86e1b-231">**Nome valore**</span><span class="sxs-lookup"><span data-stu-id="86e1b-231">**Value name**</span></span> <br/> |<span data-ttu-id="86e1b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="86e1b-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="86e1b-233">**Tipo valore**</span><span class="sxs-lookup"><span data-stu-id="86e1b-233">**Value type**</span></span> <br/> |<span data-ttu-id="86e1b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="86e1b-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="86e1b-235">**Dati valore**</span><span class="sxs-lookup"><span data-stu-id="86e1b-235">**Value data**</span></span> <br/> |<span data-ttu-id="86e1b-236">00000000</span><span class="sxs-lookup"><span data-stu-id="86e1b-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="86e1b-237">Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="86e1b-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="86e1b-238">Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="86e1b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="86e1b-239">Per usare l'oggetto Criteri di gruppo per assegnare il criterio</span><span class="sxs-lookup"><span data-stu-id="86e1b-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="86e1b-240">In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="86e1b-241">Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="86e1b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="86e1b-242">Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="86e1b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="86e1b-243">Al prompt dei comandi digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="86e1b-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="86e1b-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="86e1b-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="86e1b-245">Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="86e1b-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="86e1b-246">Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="86e1b-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="86e1b-247">Aprire l'editor del registro di sistema e passare alla chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** .</span><span class="sxs-lookup"><span data-stu-id="86e1b-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="86e1b-248">Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.</span><span class="sxs-lookup"><span data-stu-id="86e1b-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

