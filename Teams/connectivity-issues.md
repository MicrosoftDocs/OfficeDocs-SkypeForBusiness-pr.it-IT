---
title: Risolvere i problemi di connettività con client Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: ee6cb916388dbfc0109185a0280da052980f8ccd
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137756"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="cf62f-103">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf62f-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="cf62f-104">La maggior parte dei problemi riscontrati con il client di Microsoft Teams può essere ricondotta al firewall o alla connessione proxy.</span><span class="sxs-lookup"><span data-stu-id="cf62f-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="cf62f-105">Per ridurre al minimo l'uso non necessario della funzionalità Risoluzione dei problemi, è opportuno controllare che gli opportuni URL, indirizzi IP e porte siano aperti nel firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="cf62f-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="cf62f-106">Per informazioni specifiche sugli URL e gli indirizzi IP necessari per Microsoft Teams, vedere l'articolo del supporto [URL e indirizzi IP di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="cf62f-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="cf62f-107">Per gli scenari seguenti è necessario che gli URL e le porte specifici siano aperti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="cf62f-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="cf62f-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cf62f-108">Authentication</span></span>

-   <span data-ttu-id="cf62f-109">Connettività del client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf62f-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="cf62f-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="cf62f-110">Collaboration</span></span>

-   <span data-ttu-id="cf62f-111">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="cf62f-111">Media</span></span>

-   <span data-ttu-id="cf62f-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="cf62f-112">Shared Services</span></span>

-   <span data-ttu-id="cf62f-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="cf62f-113">Third Party Integration</span></span>

-   <span data-ttu-id="cf62f-114">Interoperabilità di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf62f-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="cf62f-115">Interoperabilità del client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf62f-115">Skype for Business Client Interoperability</span></span>
