---
title: 'Lync Server 2013: Configurazione della pagina di partecipazione alle riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8471b6b897a365763d55edcbd55e4a9bab4a3124
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="25c5c-102">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25c5c-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25c5c-103">_**Argomento Ultima modifica:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="25c5c-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="25c5c-104">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="25c5c-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="25c5c-105">Se un client è già installato, il client si apre e si unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="25c5c-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="25c5c-106">Se un client non è installato, per impostazione predefinita viene aperta la versione 2013 di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="25c5c-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="25c5c-107">È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare a riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="25c5c-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="25c5c-108">Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma le configuri usando il cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="25c5c-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="25c5c-109">Set di pagine di join di riunione-parametri di CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="25c5c-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25c5c-110">Parametro Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="25c5c-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="25c5c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25c5c-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25c5c-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="25c5c-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="25c5c-113">Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione usando Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="25c5c-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="25c5c-114">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="25c5c-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25c5c-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="25c5c-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="25c5c-116">Se impostato su true, le opzioni alternative per partecipare a una conferenza online (ad esempio Office Communicator 2007 R2) verranno espanse e visualizzate automaticamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="25c5c-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="25c5c-117">Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="25c5c-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="25c5c-118">Per configurare la pagina di partecipazione alla riunione tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="25c5c-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="25c5c-119">Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="25c5c-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="25c5c-120">Per visualizzare le impostazioni di configurazione del servizio Web, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="25c5c-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="25c5c-121">Eseguire il comando seguente, con i parametri impostati su true o false, a seconda delle preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) nella documentazione di Lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="25c5c-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25c5c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25c5c-122">See Also</span></span>


[<span data-ttu-id="25c5c-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="25c5c-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

