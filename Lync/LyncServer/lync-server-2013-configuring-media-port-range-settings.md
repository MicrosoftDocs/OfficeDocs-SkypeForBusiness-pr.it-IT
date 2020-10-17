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
ms.openlocfilehash: e13e491037346d9c3186a8f15aada949c46ac8df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502093"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="75014-102">Configurazione delle impostazioni dell'intervallo di porte multimediali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75014-102">Configuring media port range settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75014-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="75014-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="75014-104">Le impostazioni degli intervalli di porte multimediali possono influire in modo significativo sulle prestazioni del client e devono essere configurate.</span><span class="sxs-lookup"><span data-stu-id="75014-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="75014-105">È possibile configurare queste impostazioni utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75014-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="75014-106">Impostazioni intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="75014-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75014-107">Impostazione</span><span class="sxs-lookup"><span data-stu-id="75014-107">Setting</span></span></th>
<th><span data-ttu-id="75014-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75014-108">Description</span></span></th>
<th><span data-ttu-id="75014-109">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="75014-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="75014-110">Parametri cmdlet</span><span class="sxs-lookup"><span data-stu-id="75014-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75014-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="75014-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="75014-p102">Specifica se gli intervalli di porte inviati dal server devono essere usati dal client per il contenuto multimediale e la segnalazione. Viene usata con i valori secondari MinMediaPort e MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="75014-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="75014-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75014-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75014-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="75014-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75014-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="75014-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="75014-p103">Specifica il numero iniziale di porte da usare per il contenuto multimediale. Insieme a MaxMediaPort specifica l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="75014-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="75014-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75014-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75014-121">ClientMediaPort (rappresenta il numero di porta iniziale da usare per il contenuto multimediale del client)</span><span class="sxs-lookup"><span data-stu-id="75014-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75014-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="75014-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="75014-p104">Specifica il numero massimo di porte da usare per il contenuto multimediale. Insieme a MinMediaPort specifica l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="75014-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="75014-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75014-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75014-127">ClientMediaPortRange (indica il numero totale di porte disponibili per il contenuto multimediale dei client; il valore predefinito è 40)</span><span class="sxs-lookup"><span data-stu-id="75014-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="75014-128">Per configurare le impostazioni dell'intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="75014-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="75014-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="75014-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="75014-130">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="75014-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="75014-131">Questo cmdlet restituisce le impostazioni di configurazione delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="75014-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="75014-132">Eseguire il cmdlet seguente con i parametri e i valori che si desidera modificare (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server Management Shell):</span><span class="sxs-lookup"><span data-stu-id="75014-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75014-133">È possibile creare set aggiuntivi di impostazioni di configurazione delle conferenze per siti specifici.</span><span class="sxs-lookup"><span data-stu-id="75014-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="75014-134">Usare il cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> con un'identità di sito.</span><span class="sxs-lookup"><span data-stu-id="75014-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="75014-135">Quando si creano nuove impostazioni di configurazione delle conferenze per i siti, le impostazioni dei siti hanno la precedenza su quelle globali.</span><span class="sxs-lookup"><span data-stu-id="75014-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="75014-136">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75014-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

