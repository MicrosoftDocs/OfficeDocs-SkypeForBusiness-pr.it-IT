---
title: URL e intervalli di indirizzi IP di Microsoft 365 e Office 365
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094518"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP di Microsoft 365 e Office 365
=======================================================

Passare agli URL e agli intervalli di indirizzi IP di [Microsoft 365 e Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per un elenco dettagliato e aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che devono essere configurati correttamente per Teams. Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. È consigliabile [sottoscriversi tramite RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) per ricevere notifiche quando queste informazioni vengono aggiornate o modificate.

L'esperienza di chiamate e riunioni di Teams si basa sull'infrastruttura basata sul cloud di nuova generazione usata anche da Skype e Skype for Business. Questi investimenti tecnologici includono servizi cloud basati su Azure per l'elaborazione e la segnalazione multimediale, codec video H.264, codec audio SILK e Opus, resilienza della rete, telemetria e diagnostica della qualità. Di conseguenza, sono necessari URL e IP che possono essere associati sia a Skype che a Skype for Business.

Per tutti i carichi di lavoro di Microsoft 365 e Office 365, il metodo di connessione consigliato ai servizi di Teams sta ignorando il proxy di inoltro, se possibile. Quando un server proxy si trova tra un client e i data center di Office 365, i supporti multimediali potrebbero essere forzati su TCP anziché UDP, con un impatto sulla qualità dei supporti. Scaricare file PAC proxy di esempio che possono essere usati per configurare il bypass del traffico [da Gestione degli endpoint di Microsoft 365 e Office 365.](/office365/enterprise/managing-office-365-endpoints)

Se i criteri di rete e di sicurezza richiedono il flusso del traffico di Microsoft 365 o Office 365 attraverso un server proxy, assicurarsi che i requisiti precedenti siano già soddisfatti prima di distribuire Teams nell'ambiente di produzione. Per altre informazioni, vedere [Server proxy per Teams o Skype for Business online.](proxy-servers-for-skype-for-business-online.md)