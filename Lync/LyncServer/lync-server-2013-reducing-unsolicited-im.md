---
title: 'Lync Server 2013: Riduzione della messaggistica istantanea indesiderata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="7f269-102">Riduzione della messaggistica istantanea indesiderata per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f269-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f269-103">_**Argomento Ultima modifica:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="7f269-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="7f269-104">L'applicazione di filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Microsoft Lync Server 2013 con i virus più comuni con una degradazione minima dell'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="7f269-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="7f269-105">Il filtro ISTANTANEo intelligente offre gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f269-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="7f269-106">Filtro URL avanzato</span><span class="sxs-lookup"><span data-stu-id="7f269-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="7f269-107">Filtro di trasferimento file avanzato</span><span class="sxs-lookup"><span data-stu-id="7f269-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="7f269-108">Usare il filtro istantaneo intelligente per configurare i filtri per bloccare i messaggi istantanei non richiesti o potenzialmente nocivi da endpoint sconosciuti esterni al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f269-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="7f269-109">I filtri vengono configurati specificando i criteri da usare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali e file con estensioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="7f269-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="7f269-110">Prima di distribuire l'applicazione di filtro messaggi ISTANTANEi intelligente, è necessario capire in che modo vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server di Lync Server 2013 a un altro.</span><span class="sxs-lookup"><span data-stu-id="7f269-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="7f269-111">Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in un'unica organizzazione o in tutti i confini aziendali.</span><span class="sxs-lookup"><span data-stu-id="7f269-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="7f269-112">Questa coerenza si applica al modo in cui l'avviso personalizzato e i testi di avviso vengono inseriti nei messaggi e inviati attraverso i server.</span><span class="sxs-lookup"><span data-stu-id="7f269-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="7f269-113">L'opzione di filtro consigliata consiste nel consentire messaggi istantanei con collegamenti ipertestuali, ma richiede il filtro istantaneo intelligente per disabilitare il collegamento inserendo un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="7f269-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="7f269-114">Se si sceglie questa opzione, è disponibile l'opzione aggiuntiva per comporre un avviso per gli utenti che vengono visualizzati all'inizio di ogni messaggio istantaneo che contiene un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="7f269-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="7f269-115">Una seconda opzione di filtro consiste nel consentire i messaggi istantanei con collegamenti ipertestuali non modificati.</span><span class="sxs-lookup"><span data-stu-id="7f269-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="7f269-116">Se si sceglie questa opzione, è presente l'opzione aggiuntiva (scelta consigliata) per comporre un avviso per gli utenti inseriti in ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f269-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="7f269-117">Una terza opzione consiste nel bloccare tutti i messaggi istantanei che contengono collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="7f269-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="7f269-118">Se si sceglie questa opzione, il server invia un avviso all'utente.</span><span class="sxs-lookup"><span data-stu-id="7f269-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="7f269-119">È necessario scrivere questo avviso.</span><span class="sxs-lookup"><span data-stu-id="7f269-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

