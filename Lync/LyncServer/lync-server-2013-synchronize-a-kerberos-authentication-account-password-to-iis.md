---
title: Sincronizzare la password di un account di autenticazione Kerberos con IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="d4b42-102">Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4b42-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b42-103">_**Argomento Ultima modifica:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="d4b42-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="d4b42-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4b42-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="d4b42-105">In un sito i server front-end, i server Standard Edition e gli amministratori possono usare un account di autenticazione Kerberos per l'autenticazione delle richieste al servizio servizi Web.</span><span class="sxs-lookup"><span data-stu-id="d4b42-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="d4b42-106">Questa procedura consente di individuare ogni server che utilizza servizi Web in un sito a cui è stato assegnato un account Kerberos e di aggiornare le impostazioni di configurazione di Internet Information Services (IIS) per l'uso dell'account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d4b42-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="d4b42-107">Per informazioni dettagliate, vedere [impostare la password di un account di autenticazione Kerberos in un server in Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="d4b42-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="d4b42-108">Per impostare e configurare una password per l'account di autenticazione Kerberos</span><span class="sxs-lookup"><span data-stu-id="d4b42-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="d4b42-109">Accedere a un computer di origine, ad esempio fe01.contoso.com, come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4b42-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d4b42-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d4b42-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d4b42-111">Nella riga di comando di Lync Server Management Shell eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4b42-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="d4b42-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4b42-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d4b42-113">Il nome del computer di origine e del computer di destinazione deve essere un nome di dominio completo (FQDN) del server.</span><span class="sxs-lookup"><span data-stu-id="d4b42-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="d4b42-114">Non è possibile usare l'FQDN del pool a meno che il nome del pool non sia uguale al nome del computer in uso come computer di origine o di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4b42-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d4b42-115">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4b42-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

