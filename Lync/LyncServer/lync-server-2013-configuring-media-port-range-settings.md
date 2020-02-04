---
title: "Lync Server 2013: configurazione delle impostazioni dell'intervallo di porte multimediali"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="991cd-102">Configurazione delle impostazioni dell'intervallo di porte multimediali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="991cd-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="991cd-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="991cd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="991cd-104">Le impostazioni dell'intervallo di porte multimediali possono avere un impatto significativo sulle prestazioni del client e configurate.</span><span class="sxs-lookup"><span data-stu-id="991cd-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="991cd-105">Queste impostazioni possono essere configurate tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="991cd-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="991cd-106">Impostazioni dell'intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="991cd-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="991cd-107">Impostazione</span><span class="sxs-lookup"><span data-stu-id="991cd-107">Setting</span></span></th>
<th><span data-ttu-id="991cd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="991cd-108">Description</span></span></th>
<th><span data-ttu-id="991cd-109">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="991cd-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="991cd-110">Parametri cmdlet</span><span class="sxs-lookup"><span data-stu-id="991cd-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="991cd-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="991cd-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="991cd-112">Specifica se gli intervalli di porte inviati dal server devono essere usati dal client per il supporto e la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="991cd-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="991cd-113">Usato in combinazione con i sottovalori MinMediaPort e MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="991cd-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="991cd-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="991cd-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="991cd-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="991cd-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="991cd-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="991cd-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="991cd-117">Specifica il numero di porta iniziale da usare per l'elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="991cd-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="991cd-118">Combina con MaxMediaPort per specificare l'intervallo di porte.</span><span class="sxs-lookup"><span data-stu-id="991cd-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="991cd-119">L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="991cd-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="991cd-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="991cd-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="991cd-121">ClientMediaPort (rappresenta il numero di porta iniziale da usare per il supporto client)</span><span class="sxs-lookup"><span data-stu-id="991cd-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="991cd-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="991cd-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="991cd-123">Specifica il numero di porta più alto da usare per l'elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="991cd-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="991cd-124">Combina con MinMediaPort per specificare l'intervallo di porte.</span><span class="sxs-lookup"><span data-stu-id="991cd-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="991cd-125">L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="991cd-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="991cd-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="991cd-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="991cd-127">ClientMediaPortRange (indica il numero totale di porte disponibili per il supporto client; l'impostazione predefinita è 40)</span><span class="sxs-lookup"><span data-stu-id="991cd-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="991cd-128">Per configurare le impostazioni dell'intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="991cd-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="991cd-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="991cd-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="991cd-130">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="991cd-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="991cd-131">Questo cmdlet restituisce le impostazioni di configurazione per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="991cd-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="991cd-132">Eseguire il cmdlet seguente con i parametri e i valori che si desidera modificare (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server Management Shell):</span><span class="sxs-lookup"><span data-stu-id="991cd-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="991cd-133">È possibile creare ulteriori set di impostazioni di configurazione per i servizi di conferenza per siti specifici.</span><span class="sxs-lookup"><span data-stu-id="991cd-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="991cd-134">Usa il cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con un'identità del sito.</span><span class="sxs-lookup"><span data-stu-id="991cd-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="991cd-135">Quando si creano nuove impostazioni di configurazione per i servizi di conferenza per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="991cd-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="991cd-136">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="991cd-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

