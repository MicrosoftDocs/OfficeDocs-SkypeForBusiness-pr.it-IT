---
title: Teams panoramica del case study contoso vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams case study vocale per multinazionali: Panoramica della migrazione vocale'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae8a09ab48215b1915c06e46b3d6a3a693958621
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587175"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Case study contoso: panoramica Teams migrazione vocale

Questo articolo presenta un case study che illustra come una multinazionale fittizia, Contoso, ha implementato una soluzione vocale Teams per l'organizzazione.

Contoso ha distribuito Microsoft 365 Enterprise e ha indirizzato le principali decisioni di progettazione e dettagli di implementazione per i seguenti elementi: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione dei dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e audioconferenza.  

Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams comunicazioni unificate, collaborazione e voce. Per informazioni di base su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Di Microsoft, vedere tutti gli articoli di base che iniziano con la panoramica [del case study di Contoso.](/microsoft-365/enterprise/contoso-case-study)

[https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

Negli articoli principali sono disponibili informazioni su quanto segue:  

- Esigenze dell'infrastruttura IT di Contoso
- Rete
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gestione di dispositivi mobili
- Protezione delle informazioni
- Riepilogo della Microsoft 365 Enterprise sicurezza
- Team per un progetto top secret
- SharePoint Sito online per risorse digitali altamente riservate

Per informazioni sulla pianificazione di un aggiornamento, è necessario iniziare con Introduzione [all'Microsoft Teams aggiornamento.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Obiettivi aziendali di Contoso per Teams

Per eseguire la migrazione degli utenti locali a Teams comunicazioni unificate, collaborazione e voce, Contoso ha deciso gli obiettivi aziendali seguenti:

- Teams abilitazione 

  Il team di comunicazione e collaborazione unificato di Contoso ha Teams i criteri corretti per governare e abilitare la collaborazione interna ed esterna sicura. 

- Aggiornamento da Skype for Business a Teams 

  Skype for Business è stato ampiamente distribuito all'interno di Contoso. Con la necessità di allontanare i sistemi legacy, Contoso ha deciso di aggiornare i Skype for Business utenti a Teams. Per altre informazioni, vedere Case [study contoso: Teams di aggiornamento.](voice-case-study-migration-plan.md)

- Sistema telefonico  

  Skype for Business con voIP aziendale è stato ampiamente distribuito all'interno di Contoso. Con la necessità di allontanare i sistemi legacy che rappresentavano l'hop successivo per i server di mediazione, Contoso ha eseguito la migrazione dei Skype for Business voIP aziendali a Sistema telefonico. I siti contoso usava il piano per chiamate Microsoft, Sistema telefonico routing diretto o una combinazione di entrambi. Per altre informazioni, vedere Case [study contoso: Sistema telefonico](voice-case-study-phone-system.md).

- Instradamento basato sulla posizione 

  Con le sedi degli uffici nei paesi regolamentati dalla telefonia, Contoso doveva ricreare il routing Location-Based che era presente in Skype for Business nella distribuzione Sistema telefonico rete. Per altre informazioni, vedere [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md).

- Chiamate di emergenza 

  Dove è stato implementato Il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate. Per altre informazioni, vedere Caso [di studio Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)

- Audioconferenza 

  Contoso configura i numeri dei servizi di audioconferenza ospitati nel trunk SIP al provider PSTN. Per altre informazioni, vedere Case [study contoso: Audioconferenza.](voice-case-study-audio-conferencing.md) 

- Ottimizzazione del supporto locale 

  Contoso ha sfruttato l'Ottimizzazione multimediale locale in posizioni in cui aveva un unico trunk di percorso diretto Telefono Microsoft sistema che è stato sfruttato da siti remoti. Per altre informazioni, vedere [Pianificare l'ottimizzazione dei supporti locali](direct-routing-media-optimization.md) [e Configurare l'ottimizzazione dei supporti multimediali locali.](direct-routing-media-optimization-configure.md)

- Operatori automatici e code di chiamata

  Come risultato di Covid-19, Contoso voleva fornire supporto per l'addetto alla reception mentre il personale stava lavorando in remoto. Contoso ha usato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla ricezione. Per altre informazioni, vedere [Case study contoso: Operatori automatici e code di chiamata.](voice-case-study-call-queues.md)
