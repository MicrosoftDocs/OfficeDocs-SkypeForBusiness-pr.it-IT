---
title: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida'
description: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552992"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="3d949-103">Amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d949-103">Administering users in a hybrid Lync Server 2013 deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d949-104">_**Ultimo argomento modificato:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="3d949-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="3d949-105">È possibile gestire le impostazioni utente e i criteri per gli utenti migrati in Lync Online utilizzando le funzionalità di gestione utente disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d949-105">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d949-106">Per eseguire le attività di amministrazione, è necessario accedere utilizzando l'account amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="3d949-106">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="3d949-107">Spostamento degli utenti in locale</span><span class="sxs-lookup"><span data-stu-id="3d949-107">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="3d949-108">Questa sezione si applica solo agli utenti che sono stati creati e abilitati per Lync in locale e quindi spostati da una distribuzione locale a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3d949-108">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="3d949-109">Se si desidera spostare gli utenti creati in Lync Online (e non mai abilitati per Lync in una distribuzione locale), vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">spostamento di utenti da Lync Online a Lync in locale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d949-109">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="3d949-110">Eseguire i cmdlet seguenti per spostare un utente da Lync Online di nuovo in Lync locale:</span><span class="sxs-lookup"><span data-stu-id="3d949-110">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="3d949-111">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="3d949-111">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="3d949-112">Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="3d949-112">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="3d949-113">È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d949-113">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="3d949-114">**Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione di Microsoft 365 o Office 365**</span><span class="sxs-lookup"><span data-stu-id="3d949-114">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="3d949-115">Accedere all'organizzazione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="3d949-115">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="3d949-116">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="3d949-116">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="3d949-117">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="3d949-117">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="3d949-118">Un URL di esempio è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3d949-118">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="3d949-119">Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3d949-119">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="3d949-120">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="3d949-120">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="3d949-121">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3d949-121">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

