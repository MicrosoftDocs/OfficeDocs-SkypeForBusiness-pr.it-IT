---
title: Requisiti minimi di rete per l’app Riunioni Skype
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Riepilogo: informazioni per le organizzazioni che non usano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate dalle organizzazioni che lo fanno.'
ms.openlocfilehash: b79c49b1b63041e84cc74887f6693e8601ae2465f90665ff757d9d890cb330cc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283198"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisiti minimi di rete per l’app Riunioni Skype
 
**Riepilogo:**  Informazioni per le organizzazioni che non usano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate dalle organizzazioni che lo fanno. Questo articolo non è destinato agli utenti di queste app.
  
Per consentire agli utenti di usare l'app Riunioni di Skype per partecipare alle riunioni ospitate in Skype for Business Online, gli amministratori di rete delle organizzazioni che non usano Microsoft 365 o Office 365 devono consentire o rendere disponibili in altro modo fqdn, IP e porte indicati di seguito.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisiti per la connettività dell'app Skype riunioni

Le informazioni elencate di seguito sono un sottoinsieme di URL Office 365 ip e intervalli di indirizzi [IP,](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)che forniscono una maggiore profondità e saranno sempre i più aggiornati.
                    
 
|App |FQDN di destinazione  |Indirizzi IP  |Porte  |
|---|---------|---------|---------|
|**App Riunioni Skype** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Questi indirizzi IP vengono aggiornati di frequente.  Vedere [Skype for Business ip e](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) intervalli IP Office [ip](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Questi indirizzi IP vengono aggiornati di frequente.  Vedere [Skype for Business ip e](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) intervalli IP Office [ip](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Pianificare i client riunioni (App Web e app Riunioni)](meetings-clients.md)

[Distribuire client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l Skype a app Riunioni](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
