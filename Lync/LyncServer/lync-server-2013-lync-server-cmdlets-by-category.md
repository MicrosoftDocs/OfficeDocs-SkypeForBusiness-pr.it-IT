---
title: 'Lync Server 2013: cmdlet per la categoria di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9a93f338f6fd3367999a5879d222fc1e410b9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="38b6e-102">Cmdlet per la categoria di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b6e-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b6e-103">_**Ultimo argomento modificato:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="38b6e-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="38b6e-104">Microsoft Lync Server 2013 viene fornito con quasi 550 cmdlet appositamente progettati per consentire agli amministratori di gestire Lync Server dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="38b6e-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="38b6e-105">È possibile accedere ai cmdlet da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="38b6e-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="38b6e-106">È possibile recuperare informazioni della Guida relative a un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="38b6e-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="38b6e-107">Il comando precedente consente di recuperare le informazioni della Guida disponibili per il cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="38b6e-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="38b6e-108">Sostituire il riferimento a **New-CsVoicePolicy** con il nome del cmdlet per cui si desidera recuperare la Guida.</span><span class="sxs-lookup"><span data-stu-id="38b6e-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="38b6e-109">Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Microsoft Lync Server 2013, al prompt dei comandi di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="38b6e-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="38b6e-p103">In caso di dubbi sui cmdlet necessari, è disponibile anche un elenco di cmdlet suddivisi in categorie, con relativi argomenti della Guida. Si noterà che alcuni cmdlet compaiono in più di una categoria, ma si tratta di un risultato intenzionale perché significa che sono applicabili a più aree del prodotto. Quello che segue è un elenco delle categorie:</span><span class="sxs-lookup"><span data-stu-id="38b6e-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="38b6e-113">La Guida di riferimento ai cmdlet di Skype for business è stata spostata in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="38b6e-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="38b6e-114">Facendo clic sui collegamenti riportati di seguito, è possibile utilizzare la nuova pagina di docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="38b6e-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="38b6e-115">Il contenuto è ora Open Source e disponibile per i contributi comunitari tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="38b6e-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="38b6e-116">Interessati a contribuire?</span><span class="sxs-lookup"><span data-stu-id="38b6e-116">Interested in contributing?</span></span> <span data-ttu-id="38b6e-117">Consultare il file README nel repo qui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="38b6e-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38b6e-118">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="38b6e-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38b6e-119"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlet per la gestione degli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-120"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlet per l'applicazione vocale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b6e-121"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlet per la gestione dei client in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Cmdlet avanzati di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b6e-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlet per la messaggistica istantanea e la presenza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlet per la connettività PSTN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b6e-125"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlet per le conferenze in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlet per telefoni e dispositivi in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b6e-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlet per l'infrastruttura e la distribuzione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlet per la migrazione e la coesistenza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b6e-129"><a href="lync-server-2013-security-cmdlets.md">Cmdlet per la sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlet di configurazione di Lync Server Management Shell in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b6e-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlet per i ruoli del server e i servizi in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-132"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlet per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b6e-133"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlet per la gestione delle applicazioni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlet del server Chat persistente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b6e-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlet per la Federazione e l'accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38b6e-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlet per la registrazione centralizzata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b6e-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlet di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38b6e-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38b6e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38b6e-138">See Also</span></span>


[<span data-ttu-id="38b6e-139">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="38b6e-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

