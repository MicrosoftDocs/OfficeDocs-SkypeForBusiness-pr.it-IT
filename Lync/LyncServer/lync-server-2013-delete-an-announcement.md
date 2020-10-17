---
title: 'Lync Server 2013: eliminare un annuncio'
description: 'Lync Server 2013: eliminare un annuncio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 722028f684734504d86bfc986250a2a1dd17fabc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553672"
---
# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="4bae7-103">Eliminare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae7-103">Delete an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bae7-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4bae7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4bae7-105">Per eliminare un annuncio usato per le chiamate ai numeri non assegnati, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4bae7-105">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="4bae7-106">Per eliminare un annuncio</span><span class="sxs-lookup"><span data-stu-id="4bae7-106">To delete an announcement</span></span>

1.  <span data-ttu-id="4bae7-107">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4bae7-107">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4bae7-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4bae7-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4bae7-p101">Elencare tutti gli annunci disponibili nell'organizzazione. Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4bae7-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="4bae7-p102">Nell'elenco risultante individuare l'annuncio da eliminare e copiare il GUID, quindi nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4bae7-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="4bae7-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4bae7-113">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4bae7-114">Per informazioni dettagliate su altre opzioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span><span class="sxs-lookup"><span data-stu-id="4bae7-114">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bae7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bae7-115">See Also</span></span>


[<span data-ttu-id="4bae7-116">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bae7-116">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="4bae7-117">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="4bae7-117">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="4bae7-118">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="4bae7-118">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

