---
title: 'Lync Server 2013: creare un account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="60164-102">Creare un account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60164-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60164-103">_**Ultimo argomento modificato:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="60164-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="60164-104">Per eseguire correttamente questa procedura, è necessario essere connessi al server o al dominio almeno come membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="60164-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="60164-105">È possibile creare account di autenticazione Kerberos per ogni sito oppure creare un singolo account di autenticazione Kerberos e utilizzarlo per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="60164-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="60164-106">È possibile utilizzare i cmdlet di Windows PowerShell per creare e gestire gli account, tra cui l'identificazione degli account assegnati a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="60164-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="60164-107">Il generatore di topologie e il pannello di controllo di Lync Server 2013 non visualizzano gli account di autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="60164-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="60164-108">Utilizzare la procedura seguente per creare uno o più account utente da utilizzare per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="60164-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="60164-109">Per creare un account Kerberos</span><span class="sxs-lookup"><span data-stu-id="60164-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="60164-110">Come membri del gruppo Domain Admins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="60164-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="60164-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="60164-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="60164-112">Eseguire il comando seguente dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="60164-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="60164-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60164-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="60164-114">Verificare che l'oggetto Computer sia stato creato. A tale scopo aprire Utenti e computer di Active Directory, espandere il contenitore **Utenti** e quindi verificare che l'oggetto Computer per l'account utente sia presente nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="60164-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

