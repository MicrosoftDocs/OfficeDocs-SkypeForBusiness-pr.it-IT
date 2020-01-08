---
title: 'Lync Server 2013: eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="6ff24-102">Eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ff24-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ff24-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6ff24-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6ff24-104">Seguire questa procedura per eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6ff24-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="6ff24-105">Per eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="6ff24-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="6ff24-106">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ff24-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6ff24-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ff24-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ff24-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6ff24-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ff24-109">Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.</span><span class="sxs-lookup"><span data-stu-id="6ff24-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="6ff24-110">Nella pagina fare clic sul numero di accesso esterno che si vuole eliminare nell'elenco, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6ff24-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="6ff24-111">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ff24-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6ff24-112">Rimozione dei numeri di conferenza telefonica con accesso esterno con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff24-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6ff24-113">I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso possono essere eliminati usando Windows PowerShell e il cmdlet **Remove-CsDialInConferencingAccessNumber** .</span><span class="sxs-lookup"><span data-stu-id="6ff24-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="6ff24-114">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff24-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6ff24-115">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="6ff24-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="6ff24-116">Per rimuovere un determinato numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="6ff24-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="6ff24-117">Questo comando consente di eliminare il numero di accesso per i servizi di conferenza telefonica con l'identità sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="6ff24-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="6ff24-118">Per rimuovere tutti i numeri di accesso ai servizi di conferenza telefonica con chiamata in ingresso assegnati a una specifica area geografica</span><span class="sxs-lookup"><span data-stu-id="6ff24-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="6ff24-119">Questo comando Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso associati all'area nord-ovest:</span><span class="sxs-lookup"><span data-stu-id="6ff24-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="6ff24-120">Per rimuovere i numeri di accesso per i servizi di conferenza telefonica con chiamata in base alla lingua principale</span><span class="sxs-lookup"><span data-stu-id="6ff24-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="6ff24-121">Questo comando Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso in cui l'italiano è la lingua principale:</span><span class="sxs-lookup"><span data-stu-id="6ff24-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="6ff24-122">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="6ff24-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

