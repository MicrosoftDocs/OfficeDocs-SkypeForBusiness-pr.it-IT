---
title: 'Lync Server 2013: Assegnare un account di autenticazione Kerberos a un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40974141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="a5637-102">Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5637-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5637-103">_**Argomento Ultima modifica:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="a5637-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="a5637-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a5637-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a5637-105">Dopo aver creato l'account Kerberos, è necessario assegnarlo a un sito.</span><span class="sxs-lookup"><span data-stu-id="a5637-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="a5637-106">Si tratta di un sito di Lync Server 2013 e non di un sito di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5637-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="a5637-107">È possibile creare più account di autenticazione Kerberos per ogni distribuzione, ma è possibile assegnare un solo account a un sito.</span><span class="sxs-lookup"><span data-stu-id="a5637-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="a5637-108">Usare la procedura seguente per assegnare un account di autenticazione Kerberos creato in precedenza a un sito.</span><span class="sxs-lookup"><span data-stu-id="a5637-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="a5637-109">Per informazioni dettagliate sulla creazione dell'account Kerberos, vedere [creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="a5637-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="a5637-110">Per assegnare un account di autenticazione Kerberos a un sito</span><span class="sxs-lookup"><span data-stu-id="a5637-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="a5637-111">Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a5637-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="a5637-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a5637-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a5637-113">Nella riga di comando eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5637-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="a5637-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5637-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="a5637-115">Devi specificare il parametro UserAccount usando il formato dominio\utente.</span><span class="sxs-lookup"><span data-stu-id="a5637-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="a5637-116">Il formato User@Domain. Extension non è supportato per il riferimento agli oggetti computer creati per scopi di autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a5637-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="a5637-117">**Facoltativo**: è possibile che sia stato configurato un nome FQDN (Fully Qualified Domain Name) di override per i servizi Web, come per [modificare l'URL di Microsoft Services in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="a5637-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="a5637-118">In questo caso, è necessario aggiungere un nome SPN anche per questo nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="a5637-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="a5637-119">Ad esempio, se il nome di dominio completo era WebServices. contoso. local, si eseguirebbe:</span><span class="sxs-lookup"><span data-stu-id="a5637-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5637-120">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a5637-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

