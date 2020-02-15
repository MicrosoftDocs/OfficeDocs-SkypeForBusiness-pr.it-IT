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
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="01582-102">Visualizzare le impostazioni del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01582-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01582-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="01582-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="01582-104">Le configurazioni del server perimetrale generale devono essere esaminate in base ai dati del database di gestione della configurazione, per garantire che tutte le modifiche siano state documentate in base alle procedure di controllo delle modifiche definite.</span><span class="sxs-lookup"><span data-stu-id="01582-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="01582-105">Ulteriori controlli possono includere quelli descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01582-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="01582-106">Verificare gli elenchi Consenti e blocca</span><span class="sxs-lookup"><span data-stu-id="01582-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="01582-107">Verificare gli elenchi URI SIP "Consenti" e "blocca" per i domini federati, per determinare se gli spazi dei nomi elencati sono ancora validi.</span><span class="sxs-lookup"><span data-stu-id="01582-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="01582-108">È possibile utilizzare Windows PowerShell per visualizzare gli elenchi consentiti e bloccati.</span><span class="sxs-lookup"><span data-stu-id="01582-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="01582-109">Per esaminare i domini nell'elenco dei domini consentiti, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="01582-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="01582-110">Questo comando restituisce informazioni simili a quelle per i domini nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="01582-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="01582-111">Identità: contoso.com</span><span class="sxs-lookup"><span data-stu-id="01582-111">Identity : contoso.com</span></span>

<span data-ttu-id="01582-112">Dominio: contoso.com</span><span class="sxs-lookup"><span data-stu-id="01582-112">Domain : contoso.com</span></span>

<span data-ttu-id="01582-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="01582-113">ProxyFqdn :</span></span>

<span data-ttu-id="01582-114">Commento</span><span class="sxs-lookup"><span data-stu-id="01582-114">Comment :</span></span>

<span data-ttu-id="01582-115">MarkForMonitoring: false</span><span class="sxs-lookup"><span data-stu-id="01582-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="01582-116">Commento</span><span class="sxs-lookup"><span data-stu-id="01582-116">Comment :</span></span>

<span data-ttu-id="01582-117">Per esaminare i domini nell'elenco dei domini bloccati, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="01582-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="01582-118">A sua volta, verranno ricevute informazioni come questa per ogni dominio bloccato:</span><span class="sxs-lookup"><span data-stu-id="01582-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="01582-119">Identità: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="01582-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="01582-120">Dominio: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="01582-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="01582-121">Windows PowerShell consente inoltre di verificare che sia possibile connettersi ai domini nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="01582-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="01582-122">Ad esempio, questo comando consente di verificare la connessione tra il server perimetrale (TargetFqdn) e il dominio federato contoso.com:</span><span class="sxs-lookup"><span data-stu-id="01582-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="01582-123">Questo comando consente di verificare la connessione tra il server perimetrale e tutti i domini trovati nell'elenco dei domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="01582-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="01582-124">Verificare che più server perimetrali siano identici</span><span class="sxs-lookup"><span data-stu-id="01582-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="01582-125">Se in un array con bilanciamento del carico sono distribuiti più server perimetrali, è consigliabile verificare che tutti i server perimetrali della matrice siano configurati nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="01582-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="01582-126">È possibile visualizzare le impostazioni per i server perimetrali nel riquadro dei dettagli dell'estensione Lync Server 2013 per lo snap-in Gestione computer.</span><span class="sxs-lookup"><span data-stu-id="01582-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01582-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01582-127">See Also</span></span>


[<span data-ttu-id="01582-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="01582-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="01582-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="01582-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="01582-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="01582-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

