---
title: 'Lync Server 2013: riduzione della messaggistica istantanea indesiderata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="361ba-102">Riduzione della messaggistica istantanea indesiderata per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="361ba-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="361ba-103">_**Ultimo argomento modificato:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="361ba-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="361ba-104">L'applicazione del filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Microsoft Lync Server 2013 rispetto ai virus più comuni con riduzione minima dell'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="361ba-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="361ba-105">Il filtro di protezione per messaggi istantanei offre le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="361ba-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="361ba-106">Filtro URL avanzato</span><span class="sxs-lookup"><span data-stu-id="361ba-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="361ba-107">Filtro trasferimento file avanzato</span><span class="sxs-lookup"><span data-stu-id="361ba-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="361ba-p102">Utilizzare il filtro di protezione per messaggi istantanei per configurare filtri in modo da bloccare messaggi istantanei indesiderati o potenzialmente dannosi provenienti da endpoint sconosciuti esterni al firewall aziendale. Per configurare i filtri, è necessario definire i criteri da utilizzare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali e file con estensioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="361ba-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="361ba-110">Prima di distribuire l'applicazione filtro messaggi di messaggistica istantanea intelligente, è necessario comprendere il modo in cui vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server Lync Server 2013 a un altro.</span><span class="sxs-lookup"><span data-stu-id="361ba-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="361ba-111">Tali modalità sono coerenti e non dipendono dalla posizione in cui si trovano i server, ovvero se in una singola organizzazione o attraverso i confini di più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="361ba-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="361ba-112">Questa coerenza si applica al modo in cui la nota personalizzata e il testo degli avvisi vengono inseriti nei messaggi e inviati tra server.</span><span class="sxs-lookup"><span data-stu-id="361ba-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="361ba-p104">L'opzione di filtro consigliata consiste nel consentire i messaggi istantanei con collegamenti ipertestuali, ma nel richiedere al filtro di disabilitare il collegamento anteponendovi un carattere di sottolineatura. Se si sceglie questa opzione, è anche possibile scegliere di comporre una nota per gli utenti, visualizzata all'inizio di ogni messaggio istantaneo che contiene un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="361ba-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="361ba-p105">Una seconda opzione di filtro consiste nel consentire i messaggi istantanei con collegamenti ipertestuali non modificati. Se si sceglie questa opzione, è anche possibile scegliere di comporre un avviso per gli utenti (scelta consigliata) da inserire in ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="361ba-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="361ba-p106">Una terza opzione consiste nel bloccare tutti i messaggi istantanei contenenti collegamenti ipertestuali. Se si sceglie questa opzione, il server invia un avviso all'utente. È necessario scrivere questo avviso.</span><span class="sxs-lookup"><span data-stu-id="361ba-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

