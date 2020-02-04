---
title: 'Lync Server 2013: eliminare un annuncio'
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
ms.openlocfilehash: 91a15057e4785a16e7fc632422573ee02d1d920b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="989af-102">Eliminare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="989af-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="989af-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="989af-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="989af-104">Usare la procedura seguente per eliminare un annuncio usato per le chiamate a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="989af-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="989af-105">Per eliminare un annuncio</span><span class="sxs-lookup"><span data-stu-id="989af-105">To delete an announcement</span></span>

1.  <span data-ttu-id="989af-106">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="989af-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="989af-107">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="989af-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="989af-108">Elencare tutti gli annunci dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="989af-108">List all the announcements in your organization.</span></span> <span data-ttu-id="989af-109">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="989af-109">At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="989af-110">Nell'elenco risultante individuare l'annuncio che si vuole eliminare e copiare il GUID.</span><span class="sxs-lookup"><span data-stu-id="989af-110">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="989af-111">Quindi, alla riga di comando, Esegui:</span><span class="sxs-lookup"><span data-stu-id="989af-111">Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="989af-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="989af-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="989af-113">Per informazioni dettagliate su altre opzioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span><span class="sxs-lookup"><span data-stu-id="989af-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="989af-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="989af-114">See Also</span></span>


[<span data-ttu-id="989af-115">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="989af-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="989af-116">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="989af-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="989af-117">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="989af-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

