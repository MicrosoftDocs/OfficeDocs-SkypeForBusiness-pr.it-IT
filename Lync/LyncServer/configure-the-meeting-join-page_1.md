---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4de88d5c277cb1cef2decb8c51c1c87471dae77
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40980888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="7238b-102">Configurare la pagina di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="7238b-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7238b-103">_**Argomento Ultima modifica:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="7238b-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="7238b-104">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7238b-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="7238b-105">Se un client è già installato, tale client si apre e si unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="7238b-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="7238b-106">Se un client non è installato, per impostazione predefinita viene aperta la versione 2013 di Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="7238b-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="7238b-107">È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare a riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="7238b-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="7238b-108">Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma le configuri usando il cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7238b-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="7238b-109">Parametri di CsWebServiceConfiguration pagina di join della riunione</span><span class="sxs-lookup"><span data-stu-id="7238b-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7238b-110">Parametro CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7238b-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="7238b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7238b-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7238b-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="7238b-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="7238b-113">Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione usando Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7238b-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="7238b-114">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="7238b-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7238b-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="7238b-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="7238b-116">Se impostato su true, le opzioni alternative per partecipare a una conferenza online (ad esempio Office Communicator 2007 R2) verranno espanse e visualizzate automaticamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="7238b-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="7238b-117">Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="7238b-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="7238b-118">Per configurare la pagina di partecipazione alla riunione tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7238b-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="7238b-119">Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7238b-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7238b-120">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7238b-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="7238b-121">Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7238b-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="7238b-122">Eseguire il comando seguente, con i parametri impostati su true o false, a seconda delle preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="7238b-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

