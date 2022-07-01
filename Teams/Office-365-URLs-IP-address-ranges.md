---
title: URL e intervalli di indirizzi IP per Microsoft 365 e Office 365
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Informazioni su come configurare correttamente Microsoft 365 o Office 365 URL e intervalli di indirizzi IP e bypassare il proxy di inoltro quando possibile per le connessioni con il servizio Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563734"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP per Microsoft 365 e Office 365

Vai a [Microsoft 365 e Office 365 URL e intervalli di indirizzi IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato di URL, indirizzi IP, porte e protocolli che devono essere configurati correttamente per Teams. Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. È [consigliabile abbonarsi tramite RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L'esperienza di chiamate e riunioni di Teams si basa sull'infrastruttura basata sul cloud di nuova generazione usata anche da Skype e Skype for Business. Questi investimenti tecnologici includono servizi cloud basati su Azure per l'elaborazione e la segnalazione dei supporti, il codec video H.264, il codec audio SILK e Opus, la resilienza della rete, la telemetria e la diagnostica della qualità. Di conseguenza, sono necessari URL e INDIRIZZI IP che possono essere associati sia a Skype che a Skype for Business.

Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato ai servizi di Teams bypassa il proxy di inoltro, se possibile. Quando un server proxy si trova tra un client e i data center Office 365, i supporti potrebbero essere forzati su TCP invece che su UDP, con un impatto sulla qualità multimediale. Scaricare file PAC proxy di esempio che possono essere usati per configurare il bypass del traffico da [Gestione degli endpoint di Microsoft 365 e Office 365](/office365/enterprise/managing-office-365-endpoints).

Se i criteri di rete e sicurezza richiedono Microsoft 365 o Office 365 il traffico per transitare attraverso un server proxy, assicurarsi che i requisiti precedenti siano già soddisfatti prima di distribuire Teams in produzione. Per altre informazioni, vedere [Server proxy per Teams o Skype for Business online](proxy-servers-for-skype-for-business-online.md).