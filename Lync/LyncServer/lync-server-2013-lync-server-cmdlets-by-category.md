---
title: 'Lync Server 2013: cmdlet di Lync Server per categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7a5e0b3fa81d6730caed1f4ce2f89adf0d7d96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="54366-102">Cmdlet di Lync Server 2013 per categoria</span><span class="sxs-lookup"><span data-stu-id="54366-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54366-103">_**Argomento Ultima modifica:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="54366-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="54366-104">Microsoft Lync Server 2013 include quasi 550 cmdlet progettati specificamente per consentire agli amministratori di gestire Lync Server dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="54366-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="54366-105">Si accede ai cmdlet da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="54366-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="54366-106">È possibile recuperare la guida su un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="54366-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="54366-107">Il comando precedente consente di recuperare tutta la guida disponibile per il cmdlet **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="54366-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="54366-108">Sostituire il riferimento a **New-CsVoicePolicy** con il nome del cmdlet per cui si vuole recuperare la guida.</span><span class="sxs-lookup"><span data-stu-id="54366-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="54366-109">Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Microsoft Lync Server 2013, digitare quanto segue al prompt dei comandi di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="54366-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="54366-110">Se non si è certi dei cmdlet necessari, è stato fornito anche un elenco categorizzato di cmdlet e relativi argomenti della guida.</span><span class="sxs-lookup"><span data-stu-id="54366-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="54366-111">Scoprirai che alcuni dei cmdlet vengono visualizzati in più di una categoria, che è stata intenzionale quando si applicano a più aree del prodotto.</span><span class="sxs-lookup"><span data-stu-id="54366-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="54366-112">Di seguito è riportato un elenco di categorie:</span><span class="sxs-lookup"><span data-stu-id="54366-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="54366-113">Il riferimento ai cmdlet di Skype for business è stato spostato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="54366-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="54366-114">Facendo clic sui collegamenti seguenti si accede alla nuova pagina di docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="54366-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="54366-115">Il contenuto è ora aperto e disponibile per i contributi della community tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="54366-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="54366-116">Vuoi contribuire?</span><span class="sxs-lookup"><span data-stu-id="54366-116">Interested in contributing?</span></span> <span data-ttu-id="54366-117">Vedere il file README nel repository qui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="54366-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54366-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="54366-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54366-119"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlet per la gestione degli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-120"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlet per l'applicazione vocale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54366-121"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlet per la gestione dei client in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Cmdlet di VoIP aziendale avanzati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54366-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlet di messaggistica istantanea e presenza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlet di connettività PSTN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54366-125"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlet di conferenza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlet per telefoni e dispositivi in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54366-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlet per l'infrastruttura e la distribuzione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlet per la migrazione e la coesistenza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54366-129"><a href="lync-server-2013-security-cmdlets.md">Cmdlet di sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlet di configurazione di Lync Server Management Shell in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54366-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlet ruoli server e servizi in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-132"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlet per la mobilità in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54366-133"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlet per la gestione delle applicazioni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlet del server di chat persistente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54366-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlet federativo e Access esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54366-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlet di registrazione centralizzati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54366-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlet Enterprise Voice in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="54366-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54366-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54366-138">See Also</span></span>


[<span data-ttu-id="54366-139">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="54366-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

