---
title: 'Lync Server 2013: spostare gli utenti in Lync Online'
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
ms.openlocfilehash: 3dcc72c0f9934aebf28838cfd79899e1ce7aa2bc
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="23b13-102">Spostare gli utenti in Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23b13-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23b13-103">_**Ultimo argomento modificato:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="23b13-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="23b13-104">Prima di avviare la migrazione degli utenti a Lync Online, è necessario eseguire il backup dei dati degli utenti associati agli account da spostare.</span><span class="sxs-lookup"><span data-stu-id="23b13-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="23b13-105">Non tutti i dati dell'utente vengono spostati con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="23b13-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="23b13-106">Per informazioni, vedere [backup and Restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="23b13-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="23b13-107">Eseguire la migrazione delle impostazioni utente a Lync Online</span><span class="sxs-lookup"><span data-stu-id="23b13-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="23b13-108">Le impostazioni utente vengono spostate con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="23b13-108">User settings are moved with the user account.</span></span> <span data-ttu-id="23b13-109">Alcune impostazioni locali non vengono spostate con l'account utente.</span><span class="sxs-lookup"><span data-stu-id="23b13-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="23b13-110">Spostamento di utenti pilota in Lync Online</span><span class="sxs-lookup"><span data-stu-id="23b13-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="23b13-111">Prima di iniziare a spostare gli utenti in Lync Online, potrebbe essere necessario spostare alcuni utenti pilota per confermare che l'ambiente sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="23b13-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="23b13-112">È quindi possibile verificare che le funzionalità e i servizi di Lync funzionino come previsto prima di tentare di spostare altri utenti.</span><span class="sxs-lookup"><span data-stu-id="23b13-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="23b13-113">Per spostare un utente locale nel tenant di Lync Online, eseguire i cmdlet seguenti in Lync Server Management Shell, utilizzando le credenziali di amministratore per l'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b13-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="23b13-114">Sostituire "username@contoso.com" con le informazioni per l'utente che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="23b13-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="23b13-115">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente: https:// \< FQDN del pool \> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="23b13-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="23b13-116">È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b13-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="23b13-117">**Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="23b13-117">**To determine the Hosted Migration Service URL for your organization**</span></span>

1.  <span data-ttu-id="23b13-118">Accedere all'organizzazione Microsoft 365 o Office 365 come amministratore.</span><span class="sxs-lookup"><span data-stu-id="23b13-118">Login to your Microsoft 365 or Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="23b13-119">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="23b13-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="23b13-120">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="23b13-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="23b13-121">Un URL di esempio è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="23b13-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="23b13-122">Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="23b13-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="23b13-123">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="23b13-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="23b13-124">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="23b13-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="23b13-125">Spostamento degli utenti in Lync Online</span><span class="sxs-lookup"><span data-stu-id="23b13-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="23b13-126">È possibile spostare più utenti utilizzando il cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con il parametro – Filter per selezionare gli utenti che dispongono di una proprietà specifica assegnata agli account utente, ad esempio RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="23b13-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="23b13-127">È quindi possibile eseguire il piping degli utenti restituiti al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="23b13-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="23b13-128">È inoltre possibile utilizzare il parametro – OU per recuperare tutti gli utenti nell'unità organizzativa specificata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="23b13-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="23b13-129">Verificare le impostazioni e le caratteristiche dell'utente di Lync Online</span><span class="sxs-lookup"><span data-stu-id="23b13-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="23b13-130">È possibile verificare che l'utente sia stato spostato con esito positivo nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23b13-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="23b13-131">Visualizzare lo stato dell'utente nel pannello di controllo di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="23b13-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="23b13-132">L'indicatore visivo per gli utenti locali e gli utenti online è diverso.</span><span class="sxs-lookup"><span data-stu-id="23b13-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="23b13-133">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="23b13-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

