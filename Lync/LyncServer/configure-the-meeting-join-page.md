---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10700dc8a75d5c067870b53c0e0e74b7a469504a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="cbdbf-102">Configurare la pagina di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="cbdbf-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbdbf-103">_**Ultimo argomento modificato:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="cbdbf-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="cbdbf-104">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="cbdbf-105">In caso affermativo, il client viene aperto e accede alla riunione.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="cbdbf-106">Se non è installato un client, per impostazione predefinita verrà aperta la versione 2013 di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="cbdbf-107">È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="cbdbf-108">Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma è possibile configurarle utilizzando il cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="cbdbf-109">Parametri di CsWebServiceConfiguration per la pagina di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="cbdbf-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbdbf-110">Parametro di CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="cbdbf-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="cbdbf-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbdbf-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbdbf-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="cbdbf-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="cbdbf-113">Se il valore è impostato su true, gli utenti che partecipano a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione utilizzando Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="cbdbf-114">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdbf-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="cbdbf-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="cbdbf-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="cbdbf-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="cbdbf-118">Per configurare la pagina di partecipazione alle riunioni utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="cbdbf-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="cbdbf-119">Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cbdbf-120">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cbdbf-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="cbdbf-121">Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cbdbf-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="cbdbf-122">Eseguire il comando riportato di seguito, con i parametri impostati su true o false, a seconda della preferenza (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="cbdbf-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

