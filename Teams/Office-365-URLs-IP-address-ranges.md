---
title: URL e intervalli di indirizzi IP per Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Informazioni su come configurare correttamente gli URL di Office 365 e gli intervalli di indirizzi IP e ignorare il proxy forward quando possibile per le connessioni con il servizio Microsoft teams.
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
ms.openlocfilehash: 8056758fc707c53b780843f2fc25123b92f6e252
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136486"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="6bd5f-103">URL e intervalli di indirizzi IP per Office 365</span><span class="sxs-lookup"><span data-stu-id="6bd5f-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="6bd5f-104">Accedere a [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per i team.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="6bd5f-105">Microsoft migliora costantemente il servizio Office 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="6bd5f-106">Ti consigliamo di [iscriverti tramite RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="6bd5f-107">L'esperienza teams Calling and meetings si basa sull'infrastruttura basata su cloud di nuova generazione che viene usata anche da Skype e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="6bd5f-108">Questi investimenti includono servizi cloud basati su Azure per l'elaborazione e la segnalazione di elementi multimediali, codec video H. 264, codec audio in seta e Opus, resilienza della rete, telemetria e diagnostica di qualità.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="6bd5f-109">In questo modo, sono necessari URL e indirizzi IP che possono essere associati sia con Skype che con Skype for business.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="6bd5f-110">Per tutti i carichi di lavoro di Office 365, il metodo di connessione consigliato ai servizi teams sta bypassando il proxy forward, se possibile.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="6bd5f-111">Quando un server proxy si trova tra un client e i Data Center di Office 365, l'elemento multimediale potrebbe essere forzato rispetto al protocollo TCP anziché UDP, che influisce sulla qualità del supporto.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="6bd5f-112">Scaricare i file di esempio di proxy PAC che possono essere usati per configurare il bypass del traffico dalla [gestione degli endpoint di Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="6bd5f-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="6bd5f-113">Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Office 365 in un server proxy, verificare che i requisiti di cui sopra siano già soddisfatti prima di distribuire i team in produzione.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="6bd5f-114">Per altre informazioni, leggere [i server proxy per Teams o Skype for business online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6bd5f-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
