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
ms.openlocfilehash: 1e1aa407fbb1d7d8a006698d30545165352386b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="5166e-102">Configurare l'esperienza client con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5166e-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5166e-103">_**Argomento Ultima modifica:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="5166e-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="5166e-104">**Riepilogo:** Questo argomento descrive come configurare l'esperienza client per gli utenti del client Skype for business in un ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5166e-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="5166e-105">È possibile configurare l'esperienza client solo se è in uso Lync Server 2013 con l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) o versione successiva installata.</span><span class="sxs-lookup"><span data-stu-id="5166e-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="5166e-106">Per informazioni sull'aggiornamento di Lync Server 2013, vedere [aggiornamenti per Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="5166e-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="5166e-107">Skype for business offre una nuova esperienza utente basata sull'esperienza di prodotto consumer Skype.</span><span class="sxs-lookup"><span data-stu-id="5166e-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="5166e-108">Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note.</span><span class="sxs-lookup"><span data-stu-id="5166e-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="5166e-109">Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for business-](http://go.microsoft.com/fwlink/?linkid=529022)Ecco le novità.</span><span class="sxs-lookup"><span data-stu-id="5166e-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="5166e-110">Lync Server 2013 supporta la nuova esperienza client Skype for business e l'esperienza client Lync.</span><span class="sxs-lookup"><span data-stu-id="5166e-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="5166e-111">Come amministratore, puoi scegliere l'esperienza client preferita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5166e-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="5166e-112">Ad esempio, potresti voler distribuire l'esperienza del client Lync fino a quando gli utenti dell'organizzazione non saranno completamente formati nella nuova esperienza di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5166e-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="5166e-113">In alternativa, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server 2015, è possibile che tutti gli utenti abbiano la stessa esperienza client fino a quando tutti vengono aggiornati nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="5166e-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5166e-114">Se l'organizzazione ha installato sia Skype for Business Server 2015 che Lync Server 2013, l'esperienza client predefinita sarà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5166e-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="5166e-115">Quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'interfaccia utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="5166e-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="5166e-116">Dopo alcuni minuti, agli utenti viene chiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="5166e-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="5166e-117">Per altre informazioni, vedere <STRONG>prima</STRONG> di tutto avviare il comportamento del client più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5166e-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5166e-118">L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016.</span><span class="sxs-lookup"><span data-stu-id="5166e-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="5166e-119">Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="5166e-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="5166e-120">Configurare l'esperienza client</span><span class="sxs-lookup"><span data-stu-id="5166e-120">Configure the client experience</span></span>

<span data-ttu-id="5166e-121">Puoi specificare l'esperienza client che gli utenti dell'organizzazione vedranno usando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="5166e-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="5166e-122">Il comando seguente seleziona l'esperienza del client Skype for business per tutti gli utenti dell'organizzazione interessati dal criterio globale (Ricordati che i criteri per il sito o i criteri specifici dell'utente sostituiscono il criterio globale):</span><span class="sxs-lookup"><span data-stu-id="5166e-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="5166e-123">Il comando successivo seleziona l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:</span><span class="sxs-lookup"><span data-stu-id="5166e-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="5166e-124">Il comando successivo seleziona l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="5166e-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="5166e-125">Se si vuole configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente usando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici usando il cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5166e-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="5166e-126">Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'esperienza del client Skype for business:</span><span class="sxs-lookup"><span data-stu-id="5166e-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="5166e-127">Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto vendite:</span><span class="sxs-lookup"><span data-stu-id="5166e-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="5166e-128">Comportamenti del client al primo avvio</span><span class="sxs-lookup"><span data-stu-id="5166e-128">First launch client behaviors</span></span>

<span data-ttu-id="5166e-129">Per impostazione predefinita, quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se hai selezionato l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. .</span><span class="sxs-lookup"><span data-stu-id="5166e-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="5166e-130">Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="5166e-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="5166e-131">Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="5166e-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="5166e-132">Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio in uso come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5166e-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="5166e-p108">Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5166e-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="5166e-136">Nella chiave \*\* \[Microsoft\_\\Office\\Lync\\\] del\\software utente\_corrente di HKEY\*\* creare un nuovo valore **binario** .</span><span class="sxs-lookup"><span data-stu-id="5166e-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="5166e-137">**Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="5166e-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="5166e-138">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5166e-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="5166e-139">L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5166e-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="5166e-140">Controllare la visualizzazione dell'esercitazione nella schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="5166e-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="5166e-141">Quando gli utenti aprono il client Skype for business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include *7 suggerimenti veloci che la maggior parte delle persone richiede*.</span><span class="sxs-lookup"><span data-stu-id="5166e-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="5166e-142">Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:</span><span class="sxs-lookup"><span data-stu-id="5166e-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="5166e-143">Nella \*\* \[HKEY\_corrente\_del\\software\\Microsoft\\Office\\15,0\\Lync\] \*\* Key creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="5166e-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5166e-144">**Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.</span><span class="sxs-lookup"><span data-stu-id="5166e-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="5166e-145">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5166e-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="5166e-146">Disattivare l'esercitazione nel client</span><span class="sxs-lookup"><span data-stu-id="5166e-146">Turn off the client tutorial</span></span>

<span data-ttu-id="5166e-147">Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="5166e-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="5166e-148">Nella \*\* \[HKEY\_corrente\_del\\software\\Microsoft\\Office\\15,0\\Lync\] \*\* Key creare un nuovo **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="5166e-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5166e-149">**Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.</span><span class="sxs-lookup"><span data-stu-id="5166e-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="5166e-150">Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.</span><span class="sxs-lookup"><span data-stu-id="5166e-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="5166e-151">Esperienze client predefinite</span><span class="sxs-lookup"><span data-stu-id="5166e-151">Default client experiences</span></span>

<span data-ttu-id="5166e-152">Se l'organizzazione ha installato sia Skype for Business Server 2015 che Lync Server, l'esperienza del client sarà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente Skype.</span><span class="sxs-lookup"><span data-stu-id="5166e-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="5166e-153">La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="5166e-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5166e-154">Versione del server</span><span class="sxs-lookup"><span data-stu-id="5166e-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="5166e-155">Impostazione EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5166e-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="5166e-156">Esperienza client</span><span class="sxs-lookup"><span data-stu-id="5166e-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5166e-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5166e-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5166e-158">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5166e-158">Default</span></span></p></td>
<td><p><span data-ttu-id="5166e-159">Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5166e-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5166e-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5166e-161">True</span><span class="sxs-lookup"><span data-stu-id="5166e-161">True</span></span></p></td>
<td><p><span data-ttu-id="5166e-162">Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5166e-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5166e-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5166e-164">False</span><span class="sxs-lookup"><span data-stu-id="5166e-164">False</span></span></p></td>
<td><p><span data-ttu-id="5166e-165">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5166e-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5166e-166">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5166e-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-167">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5166e-167">Default</span></span></p></td>
<td><p><span data-ttu-id="5166e-168">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5166e-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5166e-169">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5166e-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-170">True</span><span class="sxs-lookup"><span data-stu-id="5166e-170">True</span></span></p></td>
<td><p><span data-ttu-id="5166e-171">Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5166e-172">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5166e-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-173">False</span><span class="sxs-lookup"><span data-stu-id="5166e-173">False</span></span></p></td>
<td><p><span data-ttu-id="5166e-174">L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</span><span class="sxs-lookup"><span data-stu-id="5166e-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5166e-175">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="5166e-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-176">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5166e-176">Default</span></span></p></td>
<td><p><span data-ttu-id="5166e-177">L'utente ha chiesto di passare all'esperienza client Lync (l'utente non può passare a Skype for business in seguito)</span><span class="sxs-lookup"><span data-stu-id="5166e-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5166e-178">La tabella seguente mostra l'esperienza del client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:</span><span class="sxs-lookup"><span data-stu-id="5166e-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5166e-179">Versione del server</span><span class="sxs-lookup"><span data-stu-id="5166e-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="5166e-180">Impostazione dell'interfaccia utente Skype</span><span class="sxs-lookup"><span data-stu-id="5166e-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="5166e-181">Interfaccia utente client = Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="5166e-182">Interfaccia utente client = Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5166e-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5166e-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5166e-184">True</span><span class="sxs-lookup"><span data-stu-id="5166e-184">True</span></span></p></td>
<td><p><span data-ttu-id="5166e-185">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5166e-186">Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5166e-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5166e-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5166e-188">False</span><span class="sxs-lookup"><span data-stu-id="5166e-188">False</span></span></p></td>
<td><p><span data-ttu-id="5166e-189">Interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5166e-190">L'utente ha chiesto di passare all'interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5166e-191">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5166e-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-192">True</span><span class="sxs-lookup"><span data-stu-id="5166e-192">True</span></span></p></td>
<td><p><span data-ttu-id="5166e-193">L'utente ha chiesto di passare a Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5166e-194">Skype for business</span><span class="sxs-lookup"><span data-stu-id="5166e-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5166e-195">Lync Server 2010 o Lync Server 2013 (con le patch corrette)</span><span class="sxs-lookup"><span data-stu-id="5166e-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-196">False</span><span class="sxs-lookup"><span data-stu-id="5166e-196">False</span></span></p></td>
<td><p><span data-ttu-id="5166e-197">Interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5166e-198">L'utente ha chiesto di passare all'interfaccia utente di Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5166e-199">Lync Server 2010 o Lync Server 2013 (senza patch)</span><span class="sxs-lookup"><span data-stu-id="5166e-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5166e-200">Predefinita</span><span class="sxs-lookup"><span data-stu-id="5166e-200">Default</span></span></p></td>
<td><p><span data-ttu-id="5166e-201">Modalità Lync (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="5166e-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="5166e-202">Interfaccia utente di Lync (non è possibile passare a Skype for business)</span><span class="sxs-lookup"><span data-stu-id="5166e-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5166e-203">Le versioni di patch necessarie per gestire la configurazione del client Skype for business sono:</span><span class="sxs-lookup"><span data-stu-id="5166e-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="5166e-204">Lync Server 2010-aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5166e-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="5166e-205">Per informazioni, vedere [aggiornamenti per Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="5166e-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="5166e-206">Lync Server 2013-aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5166e-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="5166e-207">Per informazioni, vedere [aggiornamenti per Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="5166e-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="5166e-208">Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio</span><span class="sxs-lookup"><span data-stu-id="5166e-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="5166e-p115">L'aggiornamento del Registro di sistema per la visualizzazione dell'esperienza client Lync al primo avvio del client Skype for Business da parte dell'utente deve essere eseguito una sola volta. Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0.</span><span class="sxs-lookup"><span data-stu-id="5166e-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="5166e-p116">Nella seguente procedura viene illustrato come modificare il Registro di sistema in modo che l'esperienza client Lync venga visualizzata al primo avvio del client Skype for Business da parte dell'utente. Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5166e-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="5166e-214">**Per creare il GPO**</span><span class="sxs-lookup"><span data-stu-id="5166e-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="5166e-215">Avvia la **Console Gestione Criteri di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5166e-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="5166e-216">Per informazioni su come usare la Console Gestione Criteri di gruppo, vedi [Console Gestione Criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="5166e-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="5166e-217">Fai clic con il pulsante destro del mouse sul nodo **Oggetti Criteri di gruppo** e seleziona **Nuovo** nel menu.</span><span class="sxs-lookup"><span data-stu-id="5166e-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="5166e-218">Nella finestra di dialogo **nuovo GPO** immettere un nome per il GPO, ad esempio **MakeLyncDefaultUI**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5166e-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5166e-219">Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo creato, quindi seleziona **Modifica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="5166e-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="5166e-220">Nella finestra **Editor Gestione Criteri di gruppo** espandi **Configurazione utente**, espandi **Preferenze**, quindi **Impostazioni di Windows** e seleziona il nodo **Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="5166e-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="5166e-221">Fare clic con il pulsante destro del mouse sul nodo del **Registro di sistema** e scegliere **nuova** \> **voce del registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="5166e-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="5166e-222">Nella finestra di dialogo **Nuove proprietà Registro di sistema** aggiorna i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="5166e-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5166e-223">Campo</span><span class="sxs-lookup"><span data-stu-id="5166e-223">Field</span></span></th>
    <th><span data-ttu-id="5166e-224">Valore da selezionare o immettere</span><span class="sxs-lookup"><span data-stu-id="5166e-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5166e-225"><strong>Azione</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-226"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5166e-227"><strong>Hive</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="5166e-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5166e-229"><strong>Percorso chiave</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="5166e-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5166e-231"><strong>Nome valore</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5166e-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5166e-233"><strong>Tipo valore</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="5166e-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5166e-235"><strong>Dati valore</strong></span><span class="sxs-lookup"><span data-stu-id="5166e-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="5166e-236">00000000</span><span class="sxs-lookup"><span data-stu-id="5166e-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="5166e-237">Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5166e-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="5166e-238">Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="5166e-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="5166e-239">**Per usare il GPO per assegnare il criterio**</span><span class="sxs-lookup"><span data-stu-id="5166e-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="5166e-240">In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.</span><span class="sxs-lookup"><span data-stu-id="5166e-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="5166e-241">Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="5166e-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="5166e-242">Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5166e-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="5166e-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="5166e-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="5166e-p117">Durante l'applicazione dell'oggetto Criteri di gruppo verrà visualizzato il messaggio "Aggiornamento criteri in corso...". Al termine dell'operazione verrà visualizzato il messaggio "Aggiornamento dei criteri utente completato".</span><span class="sxs-lookup"><span data-stu-id="5166e-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="5166e-246">Al prompt dei comandi digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5166e-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="5166e-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="5166e-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="5166e-248">Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="5166e-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="5166e-249">Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="5166e-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="5166e-250">Aprire l'editor del registro di sistema e passare alla chiave di \*\* \[\_Microsoft\\\\Office\] Lync del software\_\\\\utente corrente di HKEY\*\* .</span><span class="sxs-lookup"><span data-stu-id="5166e-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="5166e-251">Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.</span><span class="sxs-lookup"><span data-stu-id="5166e-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

