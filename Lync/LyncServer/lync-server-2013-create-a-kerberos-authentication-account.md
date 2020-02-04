---
title: 'Lync Server 2013: Creare un account di autenticazione Kerberos'
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
ms.openlocfilehash: 797e9216aed5d523e39dc4827d630e0cb1b857fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="f1870-102">Creare un account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1870-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1870-103">_**Argomento Ultima modifica:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="f1870-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="f1870-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio in minima parte come membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="f1870-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="f1870-105">È possibile creare account di autenticazione Kerberos per ogni sito oppure creare un singolo account di autenticazione Kerberos e usarlo per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="f1870-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="f1870-106">Puoi usare i cmdlet di Windows PowerShell per creare e gestire gli account, incluso l'identificazione degli account assegnati a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="f1870-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="f1870-107">Il generatore di topologia e il pannello di controllo di Lync Server 2013 non visualizzano gli account di autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1870-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="f1870-108">Usare la procedura seguente per creare uno o più account utente da usare per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1870-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="f1870-109">Per creare un account Kerberos</span><span class="sxs-lookup"><span data-stu-id="f1870-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="f1870-110">Come membro del gruppo Domain Admins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f1870-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="f1870-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1870-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1870-112">Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1870-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="f1870-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1870-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="f1870-114">Verificare che l'oggetto computer sia stato creato aprendo utenti e computer di Active Directory, espandere il contenitore **utenti** e quindi verificare che l'oggetto computer per l'account utente si trovi nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="f1870-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

