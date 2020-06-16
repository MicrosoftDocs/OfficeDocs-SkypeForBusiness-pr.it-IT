---
title: Cmdlet per la creazione di report di Skype for business online e REST Web Service
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40d394ba69cf017c11d4eb6cd57246a9d425c0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="1f37e-102">Cmdlet per la creazione di report di Skype for business online e REST Web Service</span><span class="sxs-lookup"><span data-stu-id="1f37e-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f37e-103">_**Ultimo argomento modificato:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="1f37e-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="1f37e-104">In combinazione con le funzionalità di Reporting, Skype for business online consente di accedere a cinque cmdlet di Windows PowerShell che consentono di generare tali report e possono essere utilizzati dagli amministratori per restituire i dati di report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1f37e-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="1f37e-105">Skype for business online include anche il resto (Representational State Transfer), che può essere utilizzato dagli sviluppatori per recuperare le informazioni di Reporting personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1f37e-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="1f37e-106">I cmdlet per i report disponibili per gli amministratori includono:</span><span class="sxs-lookup"><span data-stu-id="1f37e-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="1f37e-107">Get-CsActiveUserReport, che fornisce informazioni sul numero di utenti attivi (ovvero gli utenti che hanno effettuato l'accesso a Skype for business online e hanno partecipato a almeno una conferenza o a una sessione di comunicazione peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="1f37e-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="1f37e-108">Get-CsAVConferenceTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) degli utenti spesi nelle conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="1f37e-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="1f37e-109">Get-CsConferenceReport, che fornisce informazioni sul numero e il tipo di conferenze a cui hanno partecipato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1f37e-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="1f37e-110">Get-CsP2PAVTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) di utenti spesi nelle sessioni peer-to-peer che includevano audio e/o video.</span><span class="sxs-lookup"><span data-stu-id="1f37e-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="1f37e-111">Get-CsP2PSessionReport, che fornisce informazioni sul numero e il tipo di sessioni peer-to-peer a cui hanno partecipato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1f37e-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="1f37e-112">La maggior parte degli amministratori utilizzerà i report disponibili nell'interfaccia di amministrazione di Microsoft 365: non solo i report vengono generati automaticamente, ma forniscono anche una rappresentazione grafica dei dati che spesso è più facile interpretare rispetto ai valori dei numeri non elaborati restituiti dai cmdlet per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="1f37e-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="1f37e-113">Tuttavia, gli amministratori che hanno familiarità con Windows PowerShell possono utilizzare i cmdlet per la creazione di report per restituire dati che non sono facilmente disponibili nei report di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="1f37e-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="1f37e-114">Ad esempio, i cmdlet per i report restituiscono informazioni sulla durata della sessione (la quantità di tempo, espressa in minuti, in cui sono state riportate tutte le sessioni).</span><span class="sxs-lookup"><span data-stu-id="1f37e-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="1f37e-115">La durata delle sessioni individuali non è disponibile con i rapporti di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="1f37e-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="1f37e-116">Analogamente, nella visualizzazione giornaliera dei report di Lync Online vengono visualizzate informazioni solo per i 14 giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="1f37e-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="1f37e-117">Se si desidera esaminare i totali giornalieri per un giorno diverso, ad esempio una data di quattro mesi fa, è possibile utilizzare i cmdlet per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="1f37e-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="1f37e-118">Gli amministratori possono anche essere interessati all'articolo [utilizzo di Excel per recuperare i dati di report di office 365](https://msdn.microsoft.com/library/dn781442.aspx), in cui viene illustrato come utilizzare la funzionalità di query dei dati OData in Microsoft Excel per creare un report personalizzato di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f37e-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="1f37e-119">I report personalizzati offrono la possibilità di dettare quali dati e quanti dati vengono restituiti dal servizio Reporting di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f37e-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="1f37e-120">I report personalizzati consentono inoltre di eseguire operazioni quali la modalità di ordinamento e raggruppamento dei dati e l'accesso alle informazioni non visualizzate nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1f37e-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="1f37e-121">Gli amministratori che dispongono di uno sfondo di sviluppo possono utilizzare il servizio Web REST per ottenere informazioni non visualizzate nell'interfaccia di amministrazione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1f37e-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="1f37e-122">Il servizio REST è simile al servizio SOAP, in quanto ogni tecnologia consente di trasferire dati XML tra un client e un server.</span><span class="sxs-lookup"><span data-stu-id="1f37e-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="1f37e-123">Tuttavia, il servizio REST ha almeno due vantaggi rispetto al servizio SOAP.</span><span class="sxs-lookup"><span data-stu-id="1f37e-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="1f37e-124">Per un altro, REST esegue i trasferimenti di dati XML utilizzando un formato standardizzato noto come formato di diffusione ATOM.</span><span class="sxs-lookup"><span data-stu-id="1f37e-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="1f37e-125">Al contrario, SOAP utilizza un formato non standard per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="1f37e-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="1f37e-126">Inoltre, REST è in grado di trasferire dati tra le reti che bloccano verbi HTTP diversi da GET e POST.</span><span class="sxs-lookup"><span data-stu-id="1f37e-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1f37e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f37e-127">See Also</span></span>


<span data-ttu-id="1f37e-128">[Reporting di Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1f37e-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="1f37e-129">Servizio Web di Reporting di Office 365</span><span class="sxs-lookup"><span data-stu-id="1f37e-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="1f37e-130">Informazioni sul servizio Web di Reporting di Office 365</span><span class="sxs-lookup"><span data-stu-id="1f37e-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="1f37e-131">[Cmdlet per la creazione di rapporti di Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1f37e-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="1f37e-132">Usare Excel per recuperare dati di report Office 365</span><span class="sxs-lookup"><span data-stu-id="1f37e-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

