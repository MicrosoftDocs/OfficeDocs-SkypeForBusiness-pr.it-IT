---
title: Procedure consigliate per l'infrastruttura principale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server. Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete. Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Skype for Business Server.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815684"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="b01b1-105">Procedure consigliate per l'infrastruttura principale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b01b1-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="b01b1-106">Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server.</span><span class="sxs-lookup"><span data-stu-id="b01b1-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="b01b1-107">Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="b01b1-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="b01b1-108">Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b01b1-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="b01b1-109">Per proteggere i server della distribuzione di Skype for Business Server da danni accidentali o mirati che potrebbero causare tempi di inattività, seguire le seguenti precauzioni:</span><span class="sxs-lookup"><span data-stu-id="b01b1-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="b01b1-110">Aggiornare i server con gli aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b01b1-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="b01b1-111">La sottoscrizione al servizio di notifica della sicurezza Microsoft consente di ricevere una notifica immediata dei rilasci del Bollettino della sicurezza per qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b01b1-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="b01b1-112">Per eseguire la sottoscrizione, visitare il [sito Web Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="b01b1-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="b01b1-113">Verificare che i diritti di accesso siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="b01b1-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="b01b1-114">Conservare i server in un ambiente fisico che impedisce l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="b01b1-114">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="b01b1-115">Verificare che in tutti i server sia installato un software antivirus adeguato.</span><span class="sxs-lookup"><span data-stu-id="b01b1-115">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="b01b1-116">Tieni aggiornato il software con i file di firma del virus più recenti.</span><span class="sxs-lookup"><span data-stu-id="b01b1-116">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="b01b1-117">Usa la funzionalità di aggiornamento automatico dell'applicazione antivirus per conservare le firme del virus aggiornate.</span><span class="sxs-lookup"><span data-stu-id="b01b1-117">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="b01b1-118">È consigliabile disabilitare i servizi di sistema operativo Windows Server che non sono necessari nei computer in cui si installa Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b01b1-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="b01b1-119">Crittografare sistemi operativi e unità disco in cui i dati vengono archiviati con un sistema di crittografia completo, a meno che non sia possibile garantire il controllo costante e completo dei server, il totale isolamento fisico e la disattivazione corretta e sicura del disco sostituito o non riuscito unità.</span><span class="sxs-lookup"><span data-stu-id="b01b1-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="b01b1-120">Disabilitare tutte le porte di accesso diretto alla memoria esterna (DMA) del server, a meno che non sia possibile garantire un controllo molto limitato sull'accesso fisico ai server.</span><span class="sxs-lookup"><span data-stu-id="b01b1-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="b01b1-121">Gli attacchi basati su DMA, che possono essere avviati abbastanza facilmente, potrebbero esporre informazioni molto riservate, come le chiavi di crittografia private.</span><span class="sxs-lookup"><span data-stu-id="b01b1-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

