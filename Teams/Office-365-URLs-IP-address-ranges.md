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
description: Informazioni su come configurare correttamente gli URL di Office 365 e gli intervalli di indirizzi IP, ignorare il proxy forward, dove disponibile per le connessioni con il servizio Microsoft teams, e i requisiti per i criteri di rete e di sicurezza.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "37569838"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP per Office 365
=====================================

Accedere a [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per i team. Microsoft migliora costantemente il servizio Office 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. Ti consigliamo di [iscriverti tramite RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L'esperienza teams Calling and meetings si basa sull'infrastruttura basata su cloud di nuova generazione che viene usata anche da Skype e Skype for business. Questi investimenti includono servizi cloud basati su Azure per l'elaborazione e la segnalazione di elementi multimediali, codec video H. 264, codec audio in seta e Opus, resilienza della rete, telemetria e diagnostica di qualità. In questo modo, sono necessari URL e indirizzi IP che possono essere associati sia con Skype che con Skype for business.

Per tutti i carichi di lavoro di Office 365, il metodo di connessione consigliato ai servizi teams sta bypassando il proxy forward, se possibile. Quando un server proxy si trova tra un client e i Data Center di Office 365, l'elemento multimediale potrebbe essere forzato rispetto al protocollo TCP anziché UDP, che influisce sulla qualità del supporto. Scaricare i file di esempio di proxy PAC che possono essere usati per configurare il bypass del traffico dalla [gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Office 365 in un server proxy, verificare che i requisiti di cui sopra siano già soddisfatti prima di distribuire i team in produzione (rivedere i [server proxy per i team o Skype for business online](proxy-servers-for-skype-for-business-online.md) per le indicazioni).
