---
title: URL e intervalli di indirizzi IP per Microsoft 365 e Office 365
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
ms.openlocfilehash: 1ad3ffdfd47b67ce21fb7f47a911afa67159f3e7
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650819"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP per Microsoft 365 e Office 365
=======================================================

Passare a URL e intervalli di indirizzi IP per [Microsoft 365 e Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato di URL, indirizzi IP, porte e protocolli che devono essere configurati correttamente per Teams. Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. È consigliabile [sottoscrivere RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L'esperienza di chiamate e riunioni di Teams si basa sull'infrastruttura basata sul cloud di nuova generazione, usata anche da Skype e Skype for Business. Questi investimenti nella tecnologia includono servizi cloud basati su Azure per l'elaborazione e il traffico di segnalazione multimediali, codec video H.264, codec audio SILK e Opus, resilienza della rete, telemetria e diagnostica della qualità. Di conseguenza, sono necessari URL e IP che possono essere associati sia a Skype che a Skype for Business.

Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato ai servizi di Teams è ignorare il proxy di inoltro, se possibile. Quando un server proxy si trova tra un client e i data center di Office 365, gli elementi multimediali potrebbero essere forzati su TCP invece che SU UDP, con effetti sulla qualità dei supporti multimediali. Scaricare file PAC proxy di esempio che possono essere usati per configurare il bypass del traffico dalla [gestione degli endpoint di Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

Se i criteri di rete e sicurezza richiedono il flusso del traffico di Microsoft 365 o Office 365 attraverso un server proxy, assicurarsi che i requisiti precedenti siano già soddisfatti prima di distribuire Teams in produzione. Per altre informazioni, vedere [Server proxy per Teams o Skype for Business online.](proxy-servers-for-skype-for-business-online.md)
