---
title: 'Lync Server 2013: protezione di IIS'
description: 'Lync Server 2013: protezione di IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51161f221c7235aad04850fdccc5d5e9db5cb579
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579732"
---
# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="fc69c-103">Protezione di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc69c-103">Protecting IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc69c-104">_**Ultimo argomento modificato:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="fc69c-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="fc69c-105">In Microsoft Office Communications Server 2007 e Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) è stato eseguito con un account utente standard.</span><span class="sxs-lookup"><span data-stu-id="fc69c-105">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="fc69c-106">Ciò può causare problemi perché in caso di scadenza della password i servizi Web potrebbero non essere più disponibili e il problema è spesso difficile da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="fc69c-106">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="fc69c-107">Per evitare il problema della scadenza delle password, Microsoft Lync Server 2013 consente di creare un account computer (per un computer che in realtà non esiste) che può fungere da entità di autenticazione per tutti i computer di un sito in cui è in esecuzione IIS.</span><span class="sxs-lookup"><span data-stu-id="fc69c-107">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="fc69c-108">Poiché questi account utilizzano il protocollo di autenticazione Kerberos, vengono denominati account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fc69c-108">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="fc69c-109">In questo modo è possibile gestire tutti i server IIS utilizzando un singolo account.</span><span class="sxs-lookup"><span data-stu-id="fc69c-109">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="fc69c-110">Per eseguire i server con questa entità di autenticazione, è necessario innanzitutto creare un account computer utilizzando il cmdlet New-CsKerberosAccount; Questo account viene quindi assegnato a uno o più siti.</span><span class="sxs-lookup"><span data-stu-id="fc69c-110">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="fc69c-111">Dopo aver effettuato l'assegnazione, l'associazione tra l'account e il sito Lync Server 2013 è abilitata eseguendo il cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="fc69c-111">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="fc69c-112">Tra le altre cose, in questo modo viene creato il nome dell'entità servizio (SPN) necessario in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc69c-112">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="fc69c-113">I nomi SPN offrono alle applicazioni client un mezzo per individuare un particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="fc69c-113">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="fc69c-114">Per ulteriori informazioni, vedere [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="fc69c-114">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="fc69c-115">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="fc69c-115">Best Practices</span></span>

<span data-ttu-id="fc69c-p103">Per migliorare la sicurezza di IIS, è consigliabile implementare un account Kerberos per IIS. Se non si implementa un account Kerberos, IIS viene eseguito con un account utente standard.</span><span class="sxs-lookup"><span data-stu-id="fc69c-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

