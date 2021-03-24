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
description: Informazioni su come configurare correttamente gli URL e gli intervalli di indirizzi IP di Microsoft 365 o Office 365 e ignorare il proxy di inoltro quando possibile per le connessioni con il servizio Microsoft Teams.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094518"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="54a3c-103">URL e intervalli di indirizzi IP di Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="54a3c-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="54a3c-104">Passare agli URL e agli intervalli di indirizzi IP di [Microsoft 365 e Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per Teams.</span><span class="sxs-lookup"><span data-stu-id="54a3c-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="54a3c-105">Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="54a3c-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="54a3c-106">È consigliabile [sottoscriversi tramite RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.</span><span class="sxs-lookup"><span data-stu-id="54a3c-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="54a3c-107">L'esperienza di chiamate e riunioni di Teams si basa sull'infrastruttura basata sul cloud di nuova generazione usata anche da Skype e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="54a3c-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="54a3c-108">Questi investimenti tecnologici includono servizi cloud basati su Azure per l'elaborazione e la segnalazione multimediale, codec video H.264, codec audio SILK e Opus, resilienza della rete, telemetria e diagnostica della qualità.</span><span class="sxs-lookup"><span data-stu-id="54a3c-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="54a3c-109">Di conseguenza, sono necessari URL e IP che possono essere associati sia a Skype che a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="54a3c-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="54a3c-110">Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato ai servizi di Teams sta ignorando il proxy di inoltro, se possibile.</span><span class="sxs-lookup"><span data-stu-id="54a3c-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="54a3c-111">Quando un server proxy si trova tra un client e i data center di Office 365, i supporti multimediali potrebbero essere forzati su TCP anziché UDP, con un impatto sulla qualità dei supporti.</span><span class="sxs-lookup"><span data-stu-id="54a3c-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="54a3c-112">Scaricare file PAC proxy di esempio che possono essere usati per configurare il bypass del traffico [da Gestione degli endpoint di Microsoft 365 e Office 365.](/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="54a3c-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="54a3c-113">Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Microsoft 365 o Office 365 attraverso un server proxy, assicurarsi che i requisiti precedenti siano già soddisfatti prima di distribuire Teams nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="54a3c-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="54a3c-114">Per altre informazioni, vedere [Server proxy per Teams o Skype for Business online.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="54a3c-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>