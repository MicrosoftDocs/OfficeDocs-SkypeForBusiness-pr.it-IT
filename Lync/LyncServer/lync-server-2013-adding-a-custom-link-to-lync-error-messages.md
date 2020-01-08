---
title: 'Lync Server 2013: Aggiunta di un collegamento personalizzato ai messaggi di errore di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="42801-102">Aggiunta di un collegamento personalizzato ai messaggi di errore di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42801-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42801-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="42801-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="42801-104">Personalizzare i messaggi di errore di Lync 2013 aggiungendo un collegamento alle informazioni relative alla risoluzione dei problemi o al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="42801-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="42801-105">A questo scopo, USA i cmdlet **New-CsClientPolicy** o **Set-CsClientPolicy** Lync Server Management Shell con il parametro CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="42801-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="42801-106">Il testo del collegamento personalizzato è "fare clic qui per gli argomenti di supporto dell'amministratore" e non può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="42801-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="42801-107">Ad esempio, il comando seguente fa sì che il collegamento personalizzato venga visualizzato nell'area della nota a piè di pagina di ogni messaggio di errore di Lync 2013 e imposta la destinazione del collegamento suhttp://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="42801-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="42801-108">Usare **Grant-CsClientPolicy** per assegnare il nuovo criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="42801-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="42801-109">Per informazioni dettagliate, vedere **New-CsClientPolicy** e **Grant-CsClientPolicy** nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="42801-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

