---
title: "Lync Server 2013: impostare una password dell'account di autenticazione Kerberos in un server"
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
ms.openlocfilehash: eeb9338943d17be1c970b4aa2ffc04d5e2c8cb86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="a37bf-102">Impostare la password di un account di autenticazione Kerberos in un server di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a37bf-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37bf-103">_**Ultimo argomento modificato:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="a37bf-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="a37bf-104">Per eseguire correttamente questa procedura è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a37bf-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a37bf-105">È necessario impostare una password sull'account Kerberos per ogni sito che dispone di Front End Server, server Standard Edition e Director.</span><span class="sxs-lookup"><span data-stu-id="a37bf-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="a37bf-106">È possibile impostare la password eseguendo il cmdlet **Set-CsKerberosAccountPassword** di Windows PowerShell in un server del sito, ad esempio un front end server.</span><span class="sxs-lookup"><span data-stu-id="a37bf-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="a37bf-107">Per ogni sito, è necessario eseguire il cmdlet **Set-CsKerberosAccountPassword** .</span><span class="sxs-lookup"><span data-stu-id="a37bf-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="a37bf-108">Il cmdlet configura Internet Information Services (IIS) per il servizio servizi Web e quindi imposta la password per l'account del computer in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a37bf-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="a37bf-109">Un metodo alternativo, basato sul parametro utilizzato con il cmdlet, consente di configurare IIS in un unico server utilizzando un altro server configurato come origine per la password dell'account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a37bf-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="a37bf-110">Quando si usa il cmdlet **Set-CsKerberosAccountPassword** per impostare una password, Kerberos imposta la password su una stringa generata in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="a37bf-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="a37bf-111">Questo cmdlet consente di contattare tutte le istanze di IIS in tutti i siti centrali di Lync Server 2013 a cui è assegnato questo account.</span><span class="sxs-lookup"><span data-stu-id="a37bf-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="a37bf-112">Per impostare una password per un account di autenticazione Kerberos</span><span class="sxs-lookup"><span data-stu-id="a37bf-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="a37bf-113">Accedere a qualsiasi computer del dominio in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a37bf-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a37bf-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a37bf-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a37bf-115">Nella riga di comando eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a37bf-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="a37bf-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a37bf-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a37bf-p103">È necessario specificare il parametro UserAccount nel formato Dominio\Utente. Il formato Utente@Dominio.estensione non è supportato per fare riferimento a oggetti computer creati ai fini dell'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a37bf-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a37bf-119">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a37bf-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

