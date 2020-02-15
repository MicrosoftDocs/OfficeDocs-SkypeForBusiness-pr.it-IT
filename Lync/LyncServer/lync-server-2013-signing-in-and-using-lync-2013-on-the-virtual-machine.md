---
title: 'Lync Server 2013: accesso e utilizzo di Lync 2013 nella macchina virtuale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e530f24150bac692717cefb2412712bf3bf8dd1c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="ed05d-102">Accesso e utilizzo di Lync 2013 nella macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="ed05d-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed05d-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ed05d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ed05d-104">Dopo aver abilitato il plug-in VDI, quando l'utente accede a Lync 2013, vengono eseguiti i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ed05d-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="ed05d-105">L'utente digita le proprie credenziali nel client Lync 2013 in esecuzione nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="ed05d-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="ed05d-106">Dopo che Lync ha rilevato la disponibilità del plug-in VDI, Lync richiede all'utente di immettere nuovamente le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="ed05d-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="ed05d-107">In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="ed05d-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="ed05d-108">Lync inizia l'accoppiamento con il plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="ed05d-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="ed05d-109">Prima che l'associazione sia completata, il client visualizza due icone nella barra di stato di Lync.</span><span class="sxs-lookup"><span data-stu-id="ed05d-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="ed05d-110">L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona intermittente in basso a destra indica che l'associazione VDI è in corso, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ed05d-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="ed05d-111">![Icona di Lync VDI che mostra un accoppiamento corretto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icona di Lync VDI che mostra un accoppiamento corretto")</span><span class="sxs-lookup"><span data-stu-id="ed05d-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="ed05d-112">Dopo il completamento dell'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà utilizzato per le chiamate e indicare il corretto completamento dell'associazione VDI:</span><span class="sxs-lookup"><span data-stu-id="ed05d-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="ed05d-113">![Icona pairing VDI di Lync con esito positivo](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icona pairing VDI di Lync con esito positivo")</span><span class="sxs-lookup"><span data-stu-id="ed05d-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="ed05d-114">Dopo le coppie di Lync con il plug-in VDI, l'utente può visualizzare la propria presenza nei dispositivi compatibili con Lync che sono connessi al computer locale.</span><span class="sxs-lookup"><span data-stu-id="ed05d-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="ed05d-115">L'utente può ora inserire e rispondere alle chiamate come al solito.</span><span class="sxs-lookup"><span data-stu-id="ed05d-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

