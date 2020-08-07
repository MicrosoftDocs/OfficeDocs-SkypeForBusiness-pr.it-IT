---
title: Risolvere i problemi di connettività con client Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
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
ms.openlocfilehash: 52097d78a3eae14bcaba98fb1613092af97d302e
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581137"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="bc4ce-103">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc4ce-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="bc4ce-104">La maggior parte dei problemi riscontrati con il client di Microsoft Teams può essere ricondotta al firewall o alla connessione proxy.</span><span class="sxs-lookup"><span data-stu-id="bc4ce-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="bc4ce-105">Per ridurre al minimo l'uso non necessario della funzionalità Risoluzione dei problemi, è opportuno controllare che gli opportuni URL, indirizzi IP e porte siano aperti nel firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="bc4ce-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="bc4ce-106">Per informazioni specifiche su URL e IPs necessari per Microsoft teams, vedere gli [URL di microsoft 365 e Office 365 e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) il supporto dell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="bc4ce-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="bc4ce-107">Per gli scenari seguenti è necessario che gli URL e le porte specifici siano aperti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="bc4ce-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="bc4ce-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="bc4ce-108">Authentication</span></span>

-   <span data-ttu-id="bc4ce-109">Connettività del client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc4ce-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="bc4ce-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="bc4ce-110">Collaboration</span></span>

-   <span data-ttu-id="bc4ce-111">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="bc4ce-111">Media</span></span>

-   <span data-ttu-id="bc4ce-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="bc4ce-112">Shared Services</span></span>

-   <span data-ttu-id="bc4ce-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="bc4ce-113">Third Party Integration</span></span>

-   <span data-ttu-id="bc4ce-114">Interoperabilità di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc4ce-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="bc4ce-115">Interoperabilità del client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc4ce-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="bc4ce-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bc4ce-116">Related topics</span></span>

[<span data-ttu-id="bc4ce-117">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="bc4ce-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)