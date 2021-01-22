---
title: Risolvere i problemi di connettività con il client Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Risolvere i problemi di connettività con il client Microsoft Teams causati principalmente dal firewall o dalla connessione proxy.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918542"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="2a7bc-103">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a7bc-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="2a7bc-104">La maggior parte dei problemi riscontrati con il client di Microsoft Teams può essere ricondotta al firewall o alla connessione proxy.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="2a7bc-105">Per ridurre al minimo l'uso non necessario della funzionalità Risoluzione dei problemi, è opportuno controllare che gli opportuni URL, indirizzi IP e porte siano aperti nel firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="2a7bc-106">Per informazioni specifiche su URL e INDIRIZZI IP necessari per Microsoft Teams, vedere l'articolo di supporto per URL e indirizzi IP per [Microsoft 365 e Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="2a7bc-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="2a7bc-107">Per gli scenari seguenti è necessario che gli URL e le porte specifici siano aperti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="2a7bc-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="2a7bc-108">Authentication</span></span>

- <span data-ttu-id="2a7bc-109">Connettività del client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a7bc-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="2a7bc-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="2a7bc-110">Collaboration</span></span>

- <span data-ttu-id="2a7bc-111">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="2a7bc-111">Media</span></span>

- <span data-ttu-id="2a7bc-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="2a7bc-112">Shared Services</span></span>

- <span data-ttu-id="2a7bc-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="2a7bc-113">Third Party Integration</span></span>

- <span data-ttu-id="2a7bc-114">Interoperabilità di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2a7bc-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="2a7bc-115">Interoperabilità del client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2a7bc-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="2a7bc-116">Quando Teams è offline o in condizioni di larghezza di banda ridotta</span><span class="sxs-lookup"><span data-stu-id="2a7bc-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="2a7bc-117">La buona notizia è che Teams continua a essere in esecuzione anche quando sei offline o in condizioni di larghezza di banda ridotta.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="2a7bc-118">Teams salva tutti i messaggi non inviati per le chat esistenti (fino a 24 ore) e li invia non appena si torna online.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="2a7bc-119">Se si è offline per più di 24 ore, Teams consente di scegliere se inviare di nuovo o eliminare i messaggi non inviati.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="2a7bc-120">Stiamo lavorando all'aggiunta di questa funzionalità alle nuove chat e aggiorneremo questa documentazione non quando sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a7bc-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a7bc-121">Related topics</span></span>

[<span data-ttu-id="2a7bc-122">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="2a7bc-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
