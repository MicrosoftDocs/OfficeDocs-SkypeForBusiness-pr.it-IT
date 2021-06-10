---
title: Risolvere i problemi di connettività con Teams client
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
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856165"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="6dd16-103">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dd16-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>

<span data-ttu-id="6dd16-104">La maggior parte dei problemi riscontrati con il client di Microsoft Teams può essere ricondotta al firewall o alla connessione proxy.</span><span class="sxs-lookup"><span data-stu-id="6dd16-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="6dd16-105">Per ridurre al minimo l'uso non necessario della funzionalità Risoluzione dei problemi, è opportuno controllare che gli opportuni URL, indirizzi IP e porte siano aperti nel firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="6dd16-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="6dd16-106">Per informazioni specifiche sugli URL e gli INDIRIZZI IP necessari per Microsoft Teams, vedere l'articolo Microsoft 365 e Office 365 URL e indirizzi [IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="6dd16-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="6dd16-107">Per gli scenari seguenti è necessario che gli URL e le porte specifici siano aperti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="6dd16-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="6dd16-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="6dd16-108">Authentication</span></span>

- <span data-ttu-id="6dd16-109">Connettività del client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dd16-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="6dd16-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="6dd16-110">Collaboration</span></span>

- <span data-ttu-id="6dd16-111">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="6dd16-111">Media</span></span>

- <span data-ttu-id="6dd16-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="6dd16-112">Shared Services</span></span>

- <span data-ttu-id="6dd16-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="6dd16-113">Third Party Integration</span></span>

- <span data-ttu-id="6dd16-114">Interoperabilità di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6dd16-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="6dd16-115">Interoperabilità del client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6dd16-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="6dd16-116">Quando Teams offline o in condizioni di larghezza di banda ridotta</span><span class="sxs-lookup"><span data-stu-id="6dd16-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="6dd16-117">La buona notizia è che Teams continua a essere in esecuzione anche quando si è offline o in condizioni di larghezza di banda ridotta.</span><span class="sxs-lookup"><span data-stu-id="6dd16-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="6dd16-118">Teams salva tutti i messaggi non inviati per le chat esistenti (fino a 24 ore) e li invia non appena si torna online.</span><span class="sxs-lookup"><span data-stu-id="6dd16-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="6dd16-119">Se si è offline per più di 24 ore, Teams scegliere di inviare di nuovo o eliminare i messaggi non inviati.</span><span class="sxs-lookup"><span data-stu-id="6dd16-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="6dd16-120">Stiamo lavorando per aggiungere questa funzionalità alle nuove chat e aggiorneremo questa documentazione quando sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="6dd16-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6dd16-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6dd16-121">Related topics</span></span>

[<span data-ttu-id="6dd16-122">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="6dd16-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)