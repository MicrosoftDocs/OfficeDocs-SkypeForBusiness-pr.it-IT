---
title: URL e intervalli di indirizzi IP di Microsoft 365 e Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Informazioni su come configurare correttamente gli URL di Microsoft 365 o Office 365 e gli intervalli di indirizzi IP e ignorare il proxy inoltra, quando possibile, per le connessioni con il servizio Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582123"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="32af0-103">URL e intervalli di indirizzi IP di Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="32af0-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="32af0-104">Vedere gli [URL e gli intervalli di indirizzi IP di Microsoft 365 e Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per i team.</span><span class="sxs-lookup"><span data-stu-id="32af0-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="32af0-105">Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="32af0-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="32af0-106">Ti consigliamo di [iscriverti tramite RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.</span><span class="sxs-lookup"><span data-stu-id="32af0-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="32af0-107">L'esperienza teams Calling and meetings si basa sull'infrastruttura basata su cloud di nuova generazione che viene usata anche da Skype e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="32af0-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="32af0-108">Questi investimenti includono servizi cloud basati su Azure per l'elaborazione e la segnalazione di elementi multimediali, codec video H. 264, codec audio in seta e Opus, resilienza della rete, telemetria e diagnostica di qualità.</span><span class="sxs-lookup"><span data-stu-id="32af0-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="32af0-109">In questo modo, sono necessari URL e indirizzi IP che possono essere associati sia con Skype che con Skype for business.</span><span class="sxs-lookup"><span data-stu-id="32af0-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="32af0-110">Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato per i servizi teams sta bypassando il proxy forward, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="32af0-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="32af0-111">Quando un server proxy si trova tra un client e i Data Center di Office 365, l'elemento multimediale potrebbe essere forzato rispetto al protocollo TCP anziché UDP, che influisce sulla qualità del supporto.</span><span class="sxs-lookup"><span data-stu-id="32af0-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="32af0-112">Scaricare i file di esempio di proxy PAC che possono essere usati per configurare il bypass del traffico dalla [gestione degli endpoint di Microsoft 365 e Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="32af0-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="32af0-113">Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Microsoft 365 o Office 365 in un server proxy, verificare che i requisiti di cui sopra siano già soddisfatti prima di distribuire i team in produzione.</span><span class="sxs-lookup"><span data-stu-id="32af0-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="32af0-114">Per altre informazioni, leggere [i server proxy per Teams o Skype for business online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="32af0-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
