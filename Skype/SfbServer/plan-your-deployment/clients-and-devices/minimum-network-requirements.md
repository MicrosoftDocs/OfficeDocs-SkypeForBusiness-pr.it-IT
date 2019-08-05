---
title: Requisiti di rete minimi dell'app riunioni Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Riepilogo: informazioni per le organizzazioni che non usano Office 365 e devono accedere alle riunioni ospitate da organizzazioni che lo fanno.'
ms.openlocfilehash: 631c4b9825181300552faa387c00a1ca73097885
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "36196054"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisiti di rete minimi dell'app riunioni Skype
 
**Riepilogo:**  Informazioni per le organizzazioni che non usano Office 365 e devono accedere alle riunioni ospitate da organizzazioni che lo fanno. Questo articolo non è destinato agli utenti di queste app.
  
Per consentire agli utenti di usare l'app riunioni Skype per partecipare a riunioni ospitate in Skype for business online, gli amministratori di rete delle organizzazioni che non usano Office 365 devono inserire in whitelist o in altro modo rendere disponibili gli FQDN, gli IPs e le porte menzionati di seguito.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisiti per la connettività delle app riunioni Skype

Le informazioni elencate di seguito sono un sottoinsieme di [URL di Office 365 e intervalli di indirizzi IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), che forniscono una maggiore profondità e saranno sempre i più aggiornati.
                    
 
|App |Nomi di dominio completi di destinazione  |Indirizzi IP  |Porte  |
|---|---------|---------|---------|
|**App riunioni Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Questi indirizzi IP vengono aggiornati di frequente.  Vedere [intervalli di indirizzi IP Skype for business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e [intervalli di indirizzi IP di Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Squadre**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Questi indirizzi IP vengono aggiornati di frequente.  Vedere [intervalli di indirizzi IP Skype for business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e [intervalli di indirizzi IP di Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Pianificare i client delle riunioni (app Web e riunioni)](meetings-clients.md)

[Distribuire client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app riunioni Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
