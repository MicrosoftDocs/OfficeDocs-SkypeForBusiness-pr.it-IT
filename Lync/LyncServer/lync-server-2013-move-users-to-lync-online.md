---
title: 'Lync Server 2013: trasferire utenti in Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da56c7230f35d2f900f51b53beef98c64d1e750a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="9c842-102">Trasferire utenti a Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c842-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c842-103">_**Argomento Ultima modifica:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="9c842-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="9c842-104">Prima di iniziare la migrazione degli utenti a Lync Online, è consigliabile eseguire il backup dei dati degli utenti associati agli account da spostare.</span><span class="sxs-lookup"><span data-stu-id="9c842-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="9c842-105">Non tutti i dati degli utenti vengono spostati con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9c842-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="9c842-106">Per informazioni, vedere [requisiti di backup e ripristino in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="9c842-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="9c842-107">Eseguire la migrazione delle impostazioni utente in Lync Online</span><span class="sxs-lookup"><span data-stu-id="9c842-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="9c842-108">Le impostazioni utente vengono spostate con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9c842-108">User settings are moved with the user account.</span></span> <span data-ttu-id="9c842-109">Alcune impostazioni locali non vengono spostate con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9c842-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="9c842-110">Spostamento degli utenti pilota in Lync Online</span><span class="sxs-lookup"><span data-stu-id="9c842-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="9c842-111">Prima di iniziare a trasferire utenti in Lync Online, è consigliabile trasferire alcuni utenti pilota per verificare che l'ambiente sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9c842-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="9c842-112">Puoi quindi verificare che le caratteristiche e i servizi di Lync funzionino come previsto prima di tentare di trasferire altri utenti.</span><span class="sxs-lookup"><span data-stu-id="9c842-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="9c842-113">Per trasferire un utente locale nel tenant di Lync Online, eseguire i cmdlet seguenti in Lync Server Management Shell usando le credenziali di amministratore per il tenant di Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c842-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="9c842-114">Sostituire "username@contoso.com" con le informazioni per l'utente che si desidera trasferire.</span><span class="sxs-lookup"><span data-stu-id="9c842-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="9c842-115">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL per il pool in cui è in uso il servizio di migrazione ospitata, con il formato\<seguente:\>https://FQDN del pool/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="9c842-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="9c842-116">Per determinare l'URL del servizio di migrazione ospitata, è possibile visualizzare l'URL del pannello di controllo di Lync Online dell'account del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c842-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="9c842-117">**Per determinare l'URL del servizio di migrazione ospitata per il tenant di Office 365**</span><span class="sxs-lookup"><span data-stu-id="9c842-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="9c842-118">Accedere al tenant di Office 365 come amministratore.</span><span class="sxs-lookup"><span data-stu-id="9c842-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="9c842-119">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="9c842-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="9c842-120">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="9c842-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="9c842-121">Un URL di esempio ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9c842-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="9c842-122">Sostituire **WebDir** nell'URL con l' **amministratore**, con il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="9c842-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="9c842-123">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="9c842-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="9c842-124">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9c842-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="9c842-125">Spostamento degli utenti in Lync Online</span><span class="sxs-lookup"><span data-stu-id="9c842-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="9c842-126">Puoi trasferire più utenti usando il cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con il parametro – Filter per selezionare gli utenti con una specifica proprietà assegnata agli account utente, ad esempio RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="9c842-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="9c842-127">È quindi possibile eseguire il piping degli utenti restituiti al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9c842-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="9c842-128">Puoi anche usare il parametro – OU per recuperare tutti gli utenti nell'UO specificata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9c842-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="9c842-129">Verificare le impostazioni e le caratteristiche degli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="9c842-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="9c842-130">È possibile verificare che l'utente sia stato spostato correttamente nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c842-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="9c842-131">Visualizzare lo stato dell'utente nel pannello di controllo di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9c842-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="9c842-132">L'indicatore visivo per gli utenti locali e gli utenti online è diverso.</span><span class="sxs-lookup"><span data-stu-id="9c842-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="9c842-133">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="9c842-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

