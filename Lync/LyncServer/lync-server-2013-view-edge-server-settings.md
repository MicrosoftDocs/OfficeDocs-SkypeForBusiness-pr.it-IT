---
title: 'Lync Server 2013: visualizzare le impostazioni del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="dee0e-102">Visualizzare le impostazioni del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee0e-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee0e-103">_**Argomento Ultima modifica:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="dee0e-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="dee0e-104">Le configurazioni generali di Edge Server devono essere esaminate in base ai dati nel database di gestione della configurazione, per garantire che tutte le modifiche siano state documentate in base alle procedure di controllo delle modifiche definite.</span><span class="sxs-lookup"><span data-stu-id="dee0e-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="dee0e-105">Altri controlli potrebbero includere quelli descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dee0e-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="dee0e-106">Verificare gli elenchi Consenti e blocca</span><span class="sxs-lookup"><span data-stu-id="dee0e-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="dee0e-107">Verificare gli elenchi URI SIP "Consenti" e "blocca" per i domini federati, per determinare se gli spazi dei nomi elencati sono ancora validi.</span><span class="sxs-lookup"><span data-stu-id="dee0e-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="dee0e-108">Puoi usare Windows PowerShell per visualizzare gli elenchi consentiti e bloccati.</span><span class="sxs-lookup"><span data-stu-id="dee0e-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="dee0e-109">Per esaminare i domini nell'elenco dei domini consentiti, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="dee0e-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="dee0e-110">Questo comando restituisce informazioni simili a quelle per i domini nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="dee0e-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="dee0e-111">Identità: contoso.com</span><span class="sxs-lookup"><span data-stu-id="dee0e-111">Identity : contoso.com</span></span>

<span data-ttu-id="dee0e-112">Dominio: contoso.com</span><span class="sxs-lookup"><span data-stu-id="dee0e-112">Domain : contoso.com</span></span>

<span data-ttu-id="dee0e-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="dee0e-113">ProxyFqdn :</span></span>

<span data-ttu-id="dee0e-114">Commento</span><span class="sxs-lookup"><span data-stu-id="dee0e-114">Comment :</span></span>

<span data-ttu-id="dee0e-115">MarkForMonitoring: false</span><span class="sxs-lookup"><span data-stu-id="dee0e-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="dee0e-116">Commento</span><span class="sxs-lookup"><span data-stu-id="dee0e-116">Comment :</span></span>

<span data-ttu-id="dee0e-117">Per esaminare i domini nell'elenco dei domini bloccati, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="dee0e-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="dee0e-118">A sua volta, riceverai informazioni come questa per ogni dominio bloccato:</span><span class="sxs-lookup"><span data-stu-id="dee0e-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="dee0e-119">Identità: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="dee0e-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="dee0e-120">Dominio: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="dee0e-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="dee0e-121">Windows PowerShell consente inoltre di verificare che sia possibile connettersi ai domini nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="dee0e-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="dee0e-122">Questo comando, ad esempio, verifica la connessione tra il server perimetrale (TargetFqdn) e il dominio federato contoso.com:</span><span class="sxs-lookup"><span data-stu-id="dee0e-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="dee0e-123">Questo comando verifica la connessione tra l'Edge Server e tutti i domini trovati nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="dee0e-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="dee0e-124">Verificare che più Edge Server siano identici</span><span class="sxs-lookup"><span data-stu-id="dee0e-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="dee0e-125">Se sono distribuiti più Edge Server in un array di bilanciamento del carico, è consigliabile verificare che tutti i server perimetrali della matrice siano configurati allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="dee0e-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="dee0e-126">È possibile visualizzare le impostazioni per i server perimetrali nel riquadro dei dettagli dell'estensione Lync Server 2013 per lo snap-in Gestione computer.</span><span class="sxs-lookup"><span data-stu-id="dee0e-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dee0e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dee0e-127">See Also</span></span>


[<span data-ttu-id="dee0e-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="dee0e-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="dee0e-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="dee0e-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="dee0e-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="dee0e-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

