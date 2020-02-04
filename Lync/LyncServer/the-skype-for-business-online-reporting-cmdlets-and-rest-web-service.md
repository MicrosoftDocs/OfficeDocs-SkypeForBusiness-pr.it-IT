---
title: Cmdlet per la creazione di report di Skype for business online e servizio Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf02e845acc35ff4381b43beb91d798ec49f58d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="53d67-102">Cmdlet per la creazione di report di Skype for business online e servizio Web REST</span><span class="sxs-lookup"><span data-stu-id="53d67-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d67-103">_**Argomento Ultima modifica:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="53d67-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="53d67-104">In combinazione con le funzionalità di creazione di report, Skype for business online consente di accedere a cinque cmdlet di Windows PowerShell che consentono di generare questi report e possono essere usati anche dagli amministratori per restituire i dati di report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="53d67-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="53d67-105">Skype for business online include anche il resto (Representational State Transfer), che può essere usato dagli sviluppatori per recuperare le informazioni di Reporting personalizzate.</span><span class="sxs-lookup"><span data-stu-id="53d67-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="53d67-106">I cmdlet per la creazione di report disponibili per gli amministratori includono:</span><span class="sxs-lookup"><span data-stu-id="53d67-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="53d67-107">Get-CsActiveUserReport, che fornisce informazioni sul numero di utenti attivi, ovvero gli utenti che hanno effettuato l'accesso a Skype for business online e hanno partecipato ad almeno una conferenza o una sessione di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="53d67-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="53d67-108">Get-CsAVConferenceTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) che gli utenti hanno trascorso in conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="53d67-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="53d67-109">Get-CsConferenceReport, che fornisce informazioni sul numero e il tipo di conferenze a cui hanno partecipato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="53d67-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="53d67-110">Get-CsP2PAVTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) che gli utenti hanno trascorso nelle sessioni peer-to-peer che includevano audio e/o video.</span><span class="sxs-lookup"><span data-stu-id="53d67-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="53d67-111">Get-CsP2PSessionReport, che fornisce informazioni sul numero e il tipo di sessioni peer-to-peer a cui hanno partecipato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="53d67-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="53d67-112">La maggior parte degli amministratori utilizzerà i report disponibili nell'interfaccia di amministrazione di Microsoft 365: non solo i report vengono generati automaticamente, ma offrono anche una rappresentazione grafica dei dati spesso più facili da interpretare rispetto ai valori numerici non elaborati restituiti dall' cmdlet per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="53d67-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="53d67-113">Tuttavia, gli amministratori che hanno familiarità con Windows PowerShell possono usare i cmdlet per la creazione di report per restituire dati non prontamente disponibili nei report di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="53d67-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="53d67-114">Ad esempio, i cmdlet per la creazione di report restituiscono informazioni sulla durata della sessione (la quantità di tempo, in minuti, in cui è durata ogni sessione).</span><span class="sxs-lookup"><span data-stu-id="53d67-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="53d67-115">Le singole durata della sessione non sono disponibili con i report di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="53d67-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="53d67-116">Allo stesso modo, nella visualizzazione giornaliera i report di Lync Online visualizzano le informazioni solo per i 14 giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="53d67-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="53d67-117">Se si vuole rivedere i totali giornalieri per un giorno diverso, ad esempio una data di quattro mesi fa, è possibile usare i cmdlet per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="53d67-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="53d67-118">Gli amministratori potrebbero anche essere interessati all'articolo che [usa Excel per recuperare i dati di report di office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), che spiega come usare la caratteristica di query di dati OData in Microsoft Excel per creare report di Office 365 personalizzato.</span><span class="sxs-lookup"><span data-stu-id="53d67-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="53d67-119">I report personalizzati offrono la possibilità di dettare i dati (e la quantità di dati) restituiti dal servizio Reporting di Office 365.</span><span class="sxs-lookup"><span data-stu-id="53d67-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="53d67-120">I report personalizzati consentono inoltre di eseguire operazioni come specificare l'ordinamento e il raggruppamento dei dati e consentire l'accesso alle informazioni non visualizzate nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="53d67-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="53d67-121">Gli amministratori con uno sfondo di sviluppo possono usare il servizio Web REST per ottenere informazioni non visualizzate nell'interfaccia di amministrazione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="53d67-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="53d67-122">Il servizio REST è simile al servizio SOAP, in quanto ogni tecnologia offre un modo per trasferire dati XML tra un client e un server.</span><span class="sxs-lookup"><span data-stu-id="53d67-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="53d67-123">Tuttavia, il servizio REST ha almeno due vantaggi rispetto al servizio SOAP.</span><span class="sxs-lookup"><span data-stu-id="53d67-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="53d67-124">Per uno, REST esegue i trasferimenti di dati XML usando un formato standardizzato noto come formato di diffusione ATOM.</span><span class="sxs-lookup"><span data-stu-id="53d67-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="53d67-125">Al contrario, SOAP usa un formato non standard durante il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="53d67-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="53d67-126">Inoltre, REST è in grado di trasferire dati tra le reti che bloccano i verbi HTTP diversi da GET e POST.</span><span class="sxs-lookup"><span data-stu-id="53d67-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="53d67-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53d67-127">See Also</span></span>


<span data-ttu-id="53d67-128">[Report di Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53d67-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="53d67-129">Servizio Web Reporting di Office 365</span><span class="sxs-lookup"><span data-stu-id="53d67-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="53d67-130">Informazioni sul servizio Web Reporting di Office 365</span><span class="sxs-lookup"><span data-stu-id="53d67-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="53d67-131">[Cmdlet di report di Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="53d67-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="53d67-132">Uso di Excel per recuperare i dati di report di Office 365</span><span class="sxs-lookup"><span data-stu-id="53d67-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

