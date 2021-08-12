---
title: Microsoft 365 e Office 365 URL e intervalli di indirizzi IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Informazioni su come configurare correttamente Microsoft 365 o Office 365 URL e intervalli di indirizzi IP e ignorare il proxy di inoltro quando possibile per le connessioni con Microsoft Teams servizio.
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
ms.openlocfilehash: 9e5925a8896667adde58d71d01a062d975ea2fe1c5c1aec629af8db88c79b623
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302041"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 e Office 365 URL e intervalli di indirizzi IP
=======================================================

Passare [a URL](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) e intervalli di indirizzi IP Microsoft 365 e Office 365 per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per Teams. Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. È consigliabile [sottoscriversi tramite RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L Teams di chiamate e riunioni è basata sull'infrastruttura basata sul cloud di nuova generazione usata anche da Skype e Skype for Business. Questi investimenti tecnologici includono servizi cloud basati su Azure per l'elaborazione e la segnalazione multimediale, codec video H.264, codec audio SILK e Opus, resilienza della rete, telemetria e diagnostica della qualità. Di conseguenza, sono necessari URL e INDIRIZZI IP che possono essere associati a Skype e Skype for Business.

Per tutti Microsoft 365 e Office 365, il metodo di connessione consigliato per Teams servizi di inoltro sta ignorando il proxy di inoltro, se possibile. Quando un server proxy si trova tra un client e i data center Office 365, i supporti multimediali potrebbero essere forzati tramite TCP invece di UDP, con un impatto sulla qualità dei supporti. Scaricare file PAC proxy di esempio che possono essere usati per configurare il bypass del traffico da Gestione Microsoft 365 [e Office 365 endpoint](/office365/enterprise/managing-office-365-endpoints).

Se i criteri di rete e di sicurezza richiedono che il traffico Microsoft 365 o Office 365 fluirà attraverso un server proxy, assicurarsi che i requisiti precedenti siano già soddisfatti prima di distribuire Teams nell'ambiente di produzione. Per altre informazioni, vedere [Server proxy per Teams o Skype for Business Online.](proxy-servers-for-skype-for-business-online.md)