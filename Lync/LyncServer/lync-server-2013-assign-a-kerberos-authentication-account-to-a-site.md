---
title: 'Lync Server 2013: assegnare un account di autenticazione Kerberos a un sito'
description: 'Lync Server 2013: assegnare un account di autenticazione Kerberos a un sito.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcd80ef3ae15ae91dfab73ee8789054d897fe5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559973"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="476f3-103">Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f3-103">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="476f3-104">_**Ultimo argomento modificato:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="476f3-104">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="476f3-105">Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="476f3-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="476f3-106">Dopo aver creato un account Kerberos, è necessario assegnarlo a un sito.</span><span class="sxs-lookup"><span data-stu-id="476f3-106">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="476f3-107">Si tratta di un sito di Lync Server 2013, non di un sito di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="476f3-107">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="476f3-108">È possibile creare più account di autenticazione Kerberos per distribuzione, ma è possibile assegnare un solo account a un sito.</span><span class="sxs-lookup"><span data-stu-id="476f3-108">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="476f3-109">Utilizzare la procedura seguente per assegnare a un sito un account di autenticazione Kerberos creato precedentemente.</span><span class="sxs-lookup"><span data-stu-id="476f3-109">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="476f3-110">Per informazioni dettagliate sulla creazione dell'account Kerberos, vedere [creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="476f3-110">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="476f3-111">Per assegnare un account di autenticazione Kerberos a un sito</span><span class="sxs-lookup"><span data-stu-id="476f3-111">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="476f3-112">Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="476f3-112">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="476f3-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="476f3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="476f3-114">Nella riga di comando eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="476f3-114">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="476f3-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="476f3-115">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="476f3-p102">È necessario specificare il parametro UserAccount utilizzando il formato Dominio\Utente. Il formato Utente@Dominio.estensione non è supportato per fare riferimento agli oggetti computer creati per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="476f3-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="476f3-118">**Facoltativo**: è possibile che sia stata configurata una sostituzione FQDN (nome di dominio completo) per i servizi Web, in base alla [modifica dell'URL dei Services in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="476f3-118">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="476f3-119">In tal caso, sarà necessario aggiungere anche un nome SPN per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="476f3-119">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="476f3-120">Ad esempio, se il nome di dominio completo è WebServices. contoso. local, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="476f3-120">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="476f3-121">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="476f3-121">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

