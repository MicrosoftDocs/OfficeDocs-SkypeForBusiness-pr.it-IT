---
title: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida'
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
ms.openlocfilehash: 15585b5df4a2c38c4d72733b8c999556e6cb8467
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521243"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="9806a-102">Amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9806a-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9806a-103">_**Ultimo argomento modificato:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="9806a-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="9806a-104">È possibile gestire le impostazioni utente e i criteri per gli utenti migrati in Lync Online utilizzando le funzionalità di gestione utente disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9806a-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9806a-105">Per eseguire le attività di amministrazione, è necessario accedere utilizzando l'account amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="9806a-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="9806a-106">Spostamento degli utenti in locale</span><span class="sxs-lookup"><span data-stu-id="9806a-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="9806a-107">Questa sezione si applica solo agli utenti che sono stati creati e abilitati per Lync in locale e quindi spostati da una distribuzione locale a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9806a-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="9806a-108">Se si desidera spostare gli utenti creati in Lync Online (e non mai abilitati per Lync in una distribuzione locale), vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">spostamento di utenti da Lync Online a Lync in locale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9806a-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="9806a-109">Eseguire i cmdlet seguenti per spostare un utente da Lync Online di nuovo in Lync locale:</span><span class="sxs-lookup"><span data-stu-id="9806a-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="9806a-110">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="9806a-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="9806a-111">Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="9806a-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="9806a-112">È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9806a-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="9806a-113">**Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione di Microsoft 365 o Office 365**</span><span class="sxs-lookup"><span data-stu-id="9806a-113">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="9806a-114">Accedere all'organizzazione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="9806a-114">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="9806a-115">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="9806a-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="9806a-116">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="9806a-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="9806a-117">Un URL di esempio è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9806a-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="9806a-118">Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9806a-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="9806a-119">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="9806a-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="9806a-120">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9806a-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

