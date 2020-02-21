---
title: Configurare il client Skype for business in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b89457c35bc9c9c0150b84ab34f4103776206ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="5e6ca-102">Configurare l'esperienza client con Skype for business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e6ca-103">_**Ultimo argomento modificato:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="5e6ca-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="5e6ca-104">**Riepilogo:** In questo argomento viene descritto come configurare l'esperienza client per gli utenti di client Skype for business in un ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="5e6ca-105">È possibile configurare l'esperienza client solo se è in esecuzione Lync Server 2013 con l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="5e6ca-106">Per informazioni sull'aggiornamento di Lync Server 2013, vedere [Updates for Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="5e6ca-107">Skype for business offre una nuova esperienza utente basata sull'esperienza del prodotto consumer Skype.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="5e6ca-108">Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="5e6ca-109">Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for Business--vedere What ' s New](https://go.microsoft.com/fwlink/?linkid=529022).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="5e6ca-110">Lync Server 2013 supporta la nuova esperienza client Skype for business e l'esperienza client Lync.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="5e6ca-111">In qualità di amministratore, è possibile scegliere l'esperienza client preferita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="5e6ca-112">Ad esempio, è possibile distribuire l'esperienza client di Lync fino a quando gli utenti dell'organizzazione non sono completamente formati nella nuova esperienza Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="5e6ca-113">In alternativa, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server 2015, è possibile che tutti gli utenti abbiano la stessa esperienza client finché non vengono aggiornati tutti al nuovo server.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5e6ca-114">Se nell'organizzazione sono stati distribuiti sia Skype for Business Server 2015 che Lync Server 2013, l'esperienza client predefinita diventerà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="5e6ca-115">Quando gli utenti lanciano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'interfaccia utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="5e6ca-116">Dopo alcuni minuti, agli utenti viene richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="5e6ca-117">Per ulteriori informazioni, vedere <STRONG>First Launch client Behavior</STRONG> più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5e6ca-118">L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="5e6ca-119">Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non venga avviata con il numero 16. ad esempio: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="5e6ca-120">Configurare l'esperienza client</span><span class="sxs-lookup"><span data-stu-id="5e6ca-120">Configure the client experience</span></span>

<span data-ttu-id="5e6ca-121">È possibile specificare l'esperienza client che gli utenti dell'organizzazione vedranno utilizzando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="5e6ca-122">Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti dell'organizzazione a cui è applicato il criterio globale (ricordarsi, il sito o i criteri specifici dell'utente eseguono l'override del criterio globale):</span><span class="sxs-lookup"><span data-stu-id="5e6ca-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="5e6ca-123">Il comando seguente consente di selezionare l'esperienza client di Lync per tutti gli utenti dell'organizzazione coinvolti nei criteri globali:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="5e6ca-124">Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="5e6ca-125">Se si desidera configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente utilizzando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici utilizzando il cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5e6ca-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="5e6ca-126">Ad esempio, il comando seguente consente di creare un nuovo criterio client, SalesClientUI, che seleziona l'esperienza client Skype for business:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="5e6ca-127">Il comando seguente assegna il criterio, SalesClientUI, a tutti i membri del reparto vendite:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="5e6ca-128">Primo avvio di comportamenti client</span><span class="sxs-lookup"><span data-stu-id="5e6ca-128">First launch client behaviors</span></span>

<span data-ttu-id="5e6ca-129">Per impostazione predefinita, quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. .</span><span class="sxs-lookup"><span data-stu-id="5e6ca-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="5e6ca-130">Dopo alcuni minuti, agli utenti verrà richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="5e6ca-131">Se si desidera visualizzare l'interfaccia utente di Lync quando gli utenti avviano il client Skype for business per la prima volta, attenersi alla seguente procedura prima che il client venga avviato per la prima volta dopo essere stato aggiornato:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="5e6ca-132">Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio che si sta utilizzando come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="5e6ca-133">Aggiornare il registro di sistema nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="5e6ca-134">Si consiglia di eseguire questa operazione prima che gli utenti avviino il client Skype for business ed è necessario eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="5e6ca-135">Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il registro di sistema in un computer aggiunto a un dominio, vedere la sezione più avanti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="5e6ca-136">Nella chiave \*\* \[Microsoft\_\\Office\\Lync\\\] del\\software utente\_corrente di HKEY\*\* creare un nuovo valore **binario** .</span><span class="sxs-lookup"><span data-stu-id="5e6ca-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="5e6ca-137">Il **nome del valore** deve essere **EnableSkypeUI**e i **dati del valore** devono essere impostati su **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="5e6ca-138">La chiave dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="5e6ca-139">L'interfaccia utente di Lync verrà visualizzata quando gli utenti avviano il client Skype for business per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="5e6ca-140">Controllare la visualizzazione dell'esercitazione sulla schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="5e6ca-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="5e6ca-141">Quando gli utenti aprono il client Skype for business, il comportamento predefinito consiste nel visualizzare una schermata di benvenuto che include *7 suggerimenti rapidi che la maggior parte delle persone richiede*.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="5e6ca-142">È possibile disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del registro di sistema nel computer client:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="5e6ca-143">Nella chiave \*\* \[Microsoft\_\\Office\\15,0\\Lync\] del\_software\\\\utente corrente di HKEY\*\* creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5e6ca-144">Il **nome del valore** deve essere **IsBasicTutorialSeenByUser**e i **dati del valore** devono essere impostati su **1**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="5e6ca-145">La chiave dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="5e6ca-146">Disattivare l'esercitazione del client</span><span class="sxs-lookup"><span data-stu-id="5e6ca-146">Turn off the client tutorial</span></span>

<span data-ttu-id="5e6ca-147">Se non si desidera che gli utenti siano in grado di accedere all'esercitazione, è possibile disattivare l'esercitazione client con il seguente valore del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="5e6ca-148">Nella chiave \*\* \[Microsoft\_\\Office\\15,0\\Lync\] del\_software\\\\utente corrente di HKEY\*\* creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5e6ca-149">Il **nome del valore** deve essere **TutorialFeatureEnabled**e i **dati del valore** devono essere impostati su **0**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="5e6ca-150">È possibile riattivare l'esercitazione impostando i **dati di valore** su **1**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="5e6ca-151">Esperienze client predefinite</span><span class="sxs-lookup"><span data-stu-id="5e6ca-151">Default client experiences</span></span>

<span data-ttu-id="5e6ca-152">Se l'organizzazione dispone sia di Skype for Business Server 2015 che di Lync Server distribuiti, l'esperienza client diventerà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente di Skype.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="5e6ca-153">Nella tabella seguente viene illustrata l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5e6ca-154">Versione server</span><span class="sxs-lookup"><span data-stu-id="5e6ca-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="5e6ca-155">Impostazione di EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5e6ca-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="5e6ca-156">Esperienza client</span><span class="sxs-lookup"><span data-stu-id="5e6ca-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e6ca-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-158">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5e6ca-158">Default</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e6ca-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e6ca-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-161">True</span><span class="sxs-lookup"><span data-stu-id="5e6ca-161">True</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e6ca-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-164">False</span><span class="sxs-lookup"><span data-stu-id="5e6ca-164">False</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-165">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e6ca-166">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-167">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5e6ca-167">Default</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-168">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-169">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-170">True</span><span class="sxs-lookup"><span data-stu-id="5e6ca-170">True</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e6ca-172">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-173">False</span><span class="sxs-lookup"><span data-stu-id="5e6ca-173">False</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-174">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-175">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-176">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5e6ca-176">Default</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-177">L'utente ha chiesto di passare a Lync Client Experience (l'utente non può passare a Skype for business in un secondo momento)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e6ca-178">La tabella successiva Visualizza l'esperienza client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5e6ca-179">Versione server</span><span class="sxs-lookup"><span data-stu-id="5e6ca-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="5e6ca-180">Impostazione dell'interfaccia utente di Skype</span><span class="sxs-lookup"><span data-stu-id="5e6ca-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="5e6ca-181">Client UI = Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="5e6ca-182">Client UI = Skype for business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e6ca-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-184">True</span><span class="sxs-lookup"><span data-stu-id="5e6ca-184">True</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-185">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e6ca-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e6ca-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-188">False</span><span class="sxs-lookup"><span data-stu-id="5e6ca-188">False</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-189">Interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-190">L'utente ha chiesto di passare all'interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-191">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-192">True</span><span class="sxs-lookup"><span data-stu-id="5e6ca-192">True</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-193">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e6ca-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e6ca-195">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-196">False</span><span class="sxs-lookup"><span data-stu-id="5e6ca-196">False</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-197">Interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-198">L'utente ha chiesto di passare all'interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e6ca-199">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-200">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5e6ca-200">Default</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-201">Modalità Lync (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="5e6ca-202">Lync UI (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e6ca-203">Le versioni delle patch necessarie per gestire la configurazione del client Skype for business sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="5e6ca-204">Lync Server 2010-February 2015 Cumulative Update (4.0.7577.710) per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="5e6ca-205">Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="5e6ca-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="5e6ca-206">Lync Server 2013-dicembre 2014 Cumulative Update (5.0.8308.857) per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="5e6ca-207">Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="5e6ca-208">Creare un oggetto Criteri di gruppo per modificare il registro di sistema in un computer aggiunto a un dominio</span><span class="sxs-lookup"><span data-stu-id="5e6ca-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="5e6ca-209">L'aggiornamento del registro di sistema per la visualizzazione dell'esperienza client di Lync al primo avvio del client Skype for business deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="5e6ca-210">Se si utilizza un oggetto Criteri di gruppo per aggiornare il registro di sistema, è necessario definire l'oggetto per creare un nuovo valore anziché aggiornare i dati del valore.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="5e6ca-211">Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, verrà creato dal GPO e i dati del valore verranno impostati su 0.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="5e6ca-212">Nella procedura seguente viene descritto come modificare il registro di sistema in modo che l'esperienza client di Lync venga visualizzata al primo avvio di Skype for business da parte di un utente.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="5e6ca-213">È inoltre possibile utilizzare questa procedura per aggiornare il registro di sistema per disabilitare l'esercitazione introduttiva sulla schermata come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="5e6ca-214">**Per creare l'oggetto Criteri di gruppo**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="5e6ca-215">Avviare la **console di gestione di criteri di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="5e6ca-216">Per informazioni su come utilizzare la console Gestione criteri di gruppo, vedere [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="5e6ca-217">Fare clic con il pulsante destro del mouse sul nodo **oggetti Criteri di gruppo** e scegliere **nuovo** dal menu.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="5e6ca-218">Nella finestra di dialogo **nuovo oggetto Criteri** di gruppo immettere un nome per l'oggetto Criteri di gruppo, ad esempio **MakeLyncDefaultUI**, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5e6ca-219">Fare clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo appena creato e quindi scegliere **modifica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="5e6ca-220">In **Editor gestione criteri di gruppo**espandere **Configurazione utente**, espandere **Preferenze**, espandere **impostazioni di Windows**e quindi selezionare il nodo **del registro di sistema** .</span><span class="sxs-lookup"><span data-stu-id="5e6ca-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="5e6ca-221">Fare clic con il pulsante destro del mouse sul nodo **del registro di sistema** e scegliere **nuovo** \> **elemento del registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="5e6ca-222">Nella finestra di dialogo **nuove proprietà del registro di sistema** , aggiornare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e6ca-223">Campo</span><span class="sxs-lookup"><span data-stu-id="5e6ca-223">Field</span></span></th>
    <th><span data-ttu-id="5e6ca-224">Valore da selezionare o immettere</span><span class="sxs-lookup"><span data-stu-id="5e6ca-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e6ca-225"><strong>Azione</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-226"><strong>Creare</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e6ca-227"><strong>Alveare</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="5e6ca-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e6ca-229"><strong>Percorso chiave</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="5e6ca-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e6ca-231"><strong>Nome valore</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5e6ca-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e6ca-233"><strong>Tipo valore</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="5e6ca-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e6ca-235"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="5e6ca-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="5e6ca-236">00000000</span><span class="sxs-lookup"><span data-stu-id="5e6ca-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="5e6ca-237">Fare clic su **OK** per salvare le modifiche e quindi chiudere l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="5e6ca-238">Successivamente, è necessario collegare l'oggetto Criteri di gruppo creato all'insieme di utenti a cui si desidera assegnare il criterio, ad esempio un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="5e6ca-239">**Per utilizzare l'oggetto Criteri di gruppo per assegnare il criterio**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="5e6ca-240">Nella console Gestione criteri di gruppo fare clic con il pulsante destro del mouse sull'unità organizzativa a cui si desidera assegnare il criterio e quindi scegliere **collegamento a un oggetto Criteri**di sistema esistente.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="5e6ca-241">Nella finestra di dialogo **Seleziona oggetto Criteri** di gruppo selezionare l'oggetto Criteri di gruppo creato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="5e6ca-242">Nel computer dell'utente di destinazione aprire una finestra del prompt dei comandi e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="5e6ca-243">**gpupdate/target: utente**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="5e6ca-244">Il messaggio "aggiornamento dei criteri..." viene visualizzato quando viene applicato l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="5e6ca-245">Al termine dell'operazione, viene visualizzato il messaggio "aggiornamento dei criteri utente completato".</span><span class="sxs-lookup"><span data-stu-id="5e6ca-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="5e6ca-246">Al prompt dei comandi, digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="5e6ca-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="5e6ca-248">Dovrebbe essere visualizzato "oggetti Criteri di gruppo assegnati" con il nome del GPO creato in basso.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="5e6ca-249">È inoltre possibile verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il registro di sistema nel computer di un utente esaminando il registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="5e6ca-250">Aprire l'editor del registro di sistema e passare alla chiave di \*\* \[\_Microsoft\\\\Office\] Lync del software\_\\\\utente corrente di HKEY\*\* .</span><span class="sxs-lookup"><span data-stu-id="5e6ca-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="5e6ca-251">Se l'oggetto Criteri di gruppo ha aggiornato correttamente il registro di sistema, verrà visualizzato un valore denominato EnableSkypeUI con un valore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

