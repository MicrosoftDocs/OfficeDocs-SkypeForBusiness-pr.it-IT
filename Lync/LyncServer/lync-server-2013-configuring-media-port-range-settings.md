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
ms.openlocfilehash: f345b97851aac264bb3b7ef05978d80d851099ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="75358-102">Configurazione delle impostazioni dell'intervallo di porte multimediali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75358-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75358-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="75358-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="75358-104">Le impostazioni degli intervalli di porte multimediali possono influire in modo significativo sulle prestazioni del client e devono essere configurate.</span><span class="sxs-lookup"><span data-stu-id="75358-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="75358-105">È possibile configurare queste impostazioni utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75358-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="75358-106">Impostazioni intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="75358-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75358-107">Impostazione</span><span class="sxs-lookup"><span data-stu-id="75358-107">Setting</span></span></th>
<th><span data-ttu-id="75358-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75358-108">Description</span></span></th>
<th><span data-ttu-id="75358-109">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="75358-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="75358-110">Parametri cmdlet</span><span class="sxs-lookup"><span data-stu-id="75358-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75358-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="75358-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="75358-p102">Specifica se gli intervalli di porte inviati dal server devono essere usati dal client per il contenuto multimediale e la segnalazione. Viene usata con i valori secondari MinMediaPort e MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="75358-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="75358-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75358-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75358-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="75358-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75358-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="75358-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="75358-p103">Specifica il numero iniziale di porte da usare per il contenuto multimediale. Insieme a MaxMediaPort specifica l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="75358-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="75358-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75358-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75358-121">ClientMediaPort (rappresenta il numero di porta iniziale da usare per il contenuto multimediale del client)</span><span class="sxs-lookup"><span data-stu-id="75358-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75358-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="75358-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="75358-p104">Specifica il numero massimo di porte da usare per il contenuto multimediale. Insieme a MinMediaPort specifica l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</span><span class="sxs-lookup"><span data-stu-id="75358-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="75358-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="75358-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="75358-127">ClientMediaPortRange (indica il numero totale di porte disponibili per il contenuto multimediale dei client; il valore predefinito è 40)</span><span class="sxs-lookup"><span data-stu-id="75358-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="75358-128">Per configurare le impostazioni dell'intervallo di porte multimediali</span><span class="sxs-lookup"><span data-stu-id="75358-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="75358-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="75358-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="75358-130">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="75358-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="75358-131">Questo cmdlet restituisce le impostazioni di configurazione delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="75358-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="75358-132">Eseguire il cmdlet seguente con i parametri e i valori che si desidera modificare (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server Management Shell):</span><span class="sxs-lookup"><span data-stu-id="75358-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75358-133">È possibile creare set aggiuntivi di impostazioni di configurazione delle conferenze per siti specifici.</span><span class="sxs-lookup"><span data-stu-id="75358-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="75358-134">Usare il cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> con un'identità di sito.</span><span class="sxs-lookup"><span data-stu-id="75358-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="75358-135">Quando si creano nuove impostazioni di configurazione delle conferenze per i siti, le impostazioni dei siti hanno la precedenza su quelle globali.</span><span class="sxs-lookup"><span data-stu-id="75358-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="75358-136">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75358-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

