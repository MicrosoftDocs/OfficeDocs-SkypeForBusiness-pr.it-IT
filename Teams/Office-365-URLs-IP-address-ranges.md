---
title: URL e intervalli di indirizzi IP di Microsoft 365 e Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 30736a347f447d265059de1a26ded5ef690e53dc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665690"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP di Microsoft 365 e Office 365
=======================================================

Vedere gli [URL e gli intervalli di indirizzi IP di Microsoft 365 e Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per i team. Microsoft migliora continuamente i servizi Microsoft 365 e Office 365 e aggiunge nuove funzionalità, ovvero le porte, gli URL e gli indirizzi IP necessari possono cambiare nel tempo. Ti consigliamo di [iscriverti tramite RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L'esperienza teams Calling and meetings si basa sull'infrastruttura basata su cloud di nuova generazione che viene usata anche da Skype e Skype for business. Questi investimenti includono servizi cloud basati su Azure per l'elaborazione e la segnalazione di elementi multimediali, codec video H. 264, codec audio in seta e Opus, resilienza della rete, telemetria e diagnostica di qualità. In questo modo, sono necessari URL e indirizzi IP che possono essere associati sia con Skype che con Skype for business.

Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato per i servizi teams sta bypassando il proxy forward, ove possibile. Quando un server proxy si trova tra un client e i Data Center di Office 365, l'elemento multimediale potrebbe essere forzato rispetto al protocollo TCP anziché UDP, che influisce sulla qualità del supporto. Scaricare i file di esempio di proxy PAC che possono essere usati per configurare il bypass del traffico dalla [gestione degli endpoint di Microsoft 365 e Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Microsoft 365 o Office 365 in un server proxy, verificare che i requisiti di cui sopra siano già soddisfatti prima di distribuire i team in produzione. Per altre informazioni, leggere [i server proxy per Teams o Skype for business online](proxy-servers-for-skype-for-business-online.md).
