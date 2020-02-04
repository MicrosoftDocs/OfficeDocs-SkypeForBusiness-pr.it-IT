---
title: 'Lync Server 2013: Impostare la password di un account di autenticazione Kerberos in un server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="796b0-102">Impostare la password di un account di autenticazione Kerberos in un server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796b0-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="796b0-103">_**Argomento Ultima modifica:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="796b0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="796b0-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="796b0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="796b0-105">È necessario configurare una password nell'account Kerberos per ogni sito che dispone di server front-end, server Standard Edition e direttori.</span><span class="sxs-lookup"><span data-stu-id="796b0-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="796b0-106">È possibile configurare la password eseguendo il cmdlet **Set-CsKerberosAccountPassword** di Windows PowerShell in un server del sito, ad esempio un server front-end.</span><span class="sxs-lookup"><span data-stu-id="796b0-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="796b0-107">Per ogni sito, è necessario eseguire il cmdlet **Set-CsKerberosAccountPassword** .</span><span class="sxs-lookup"><span data-stu-id="796b0-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="796b0-108">Il cmdlet configura Internet Information Services (IIS) per il servizio servizi Web e quindi imposta la password nell'account del computer in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="796b0-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="796b0-109">Un metodo alternativo, in base al parametro usato con il cmdlet, configura IIS su un server durante l'uso di un altro server configurato come origine della password dell'account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="796b0-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="796b0-110">Quando si usa il cmdlet **Set-CsKerberosAccountPassword** per impostare una password, Kerberos imposta la password su una stringa generata in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="796b0-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="796b0-111">Questo cmdlet Contatta tutte le istanze di IIS in tutti i siti centrali di Lync Server 2013 a cui è assegnato l'account.</span><span class="sxs-lookup"><span data-stu-id="796b0-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="796b0-112">Per impostare una password per un account di autenticazione Kerberos</span><span class="sxs-lookup"><span data-stu-id="796b0-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="796b0-113">Accedere a qualsiasi computer di dominio con Lync Server Management Shell installato come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="796b0-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="796b0-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="796b0-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="796b0-115">Nella riga di comando eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="796b0-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="796b0-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="796b0-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="796b0-117">Devi specificare il parametro UserAccount usando il formato dominio\utente.</span><span class="sxs-lookup"><span data-stu-id="796b0-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="796b0-118">Il formato User@Domain. Extension non è supportato per fare riferimento agli oggetti computer creati per scopi di autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="796b0-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="796b0-119">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="796b0-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

