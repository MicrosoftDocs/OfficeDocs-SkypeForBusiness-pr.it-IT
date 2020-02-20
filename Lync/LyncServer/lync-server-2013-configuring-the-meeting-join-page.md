---
title: 'Lync Server 2013: configurazione della pagina di partecipazione alle riunioni'
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
ms.openlocfilehash: 977903d8d85b3eaa4d944e8b3e62ec0df629c1d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="59804-102">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59804-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59804-103">_**Ultimo argomento modificato:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="59804-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="59804-104">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59804-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="59804-105">In caso affermativo, il client viene aperto e accede alla riunione.</span><span class="sxs-lookup"><span data-stu-id="59804-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="59804-106">Se non è installato un client, per impostazione predefinita verrà aperta la versione 2013 di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="59804-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="59804-107">È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="59804-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="59804-108">Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma è possibile configurarle utilizzando il cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="59804-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="59804-109">Parametri di Set-CsWebServiceConfiguration per la pagina di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="59804-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59804-110">Parametro Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="59804-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="59804-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59804-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59804-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="59804-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="59804-113">Se il valore è impostato su true, gli utenti che partecipano a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione utilizzando Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59804-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="59804-114">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="59804-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59804-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="59804-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="59804-p104">Se si imposta questo parametro su True, verranno espanse e visualizzate automaticamente agli utenti opzioni alternative per partecipare a una conferenza online, ad esempio Office Communicator 2007 R2. Se invece si imposta il parametro su False (valore predefinito), queste opzioni saranno comunque disponibili, ma l'utente dovrà visualizzare manualmente l'elenco.</span><span class="sxs-lookup"><span data-stu-id="59804-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="59804-118">Per configurare la pagina di partecipazione alle riunioni utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="59804-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="59804-119">Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="59804-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="59804-120">Per visualizzare le impostazioni dei servizi Web, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="59804-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="59804-121">Eseguire il comando riportato di seguito, con i parametri impostati su true o false, a seconda della preferenza (per informazioni dettagliate sui parametri per questo cmdlet, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) nella documentazione di Lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="59804-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59804-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59804-122">See Also</span></span>


[<span data-ttu-id="59804-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="59804-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

