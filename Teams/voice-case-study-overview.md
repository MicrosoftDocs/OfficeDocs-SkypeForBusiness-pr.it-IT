---
title: Panoramica del case study teams voice Contoso
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
description: 'Case study vocale di Teams per società multinazionali: panoramica della migrazione vocale'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808627"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Case study di Contoso: Panoramica della migrazione vocale di Teams

Questo articolo presenta un case study su come una società multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione.

Contoso ha distribuito Microsoft 365 Enterprise e ha affrontato importanti decisioni di progettazione e dettagli di implementazione per i seguenti aspetti: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione dei dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e Audioconferenza.  

Questo articolo è incentrato su come Contoso ha trasferito gli utenti locali in Teams per comunicare, collaborare e comunicare in modo unificato. Per informazioni generali su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud microsoft, vedere tutti gli articoli di base a partire dalla [panoramica del case study di Contoso](/microsoft-365/enterprise/contoso-case-study).

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

Negli articoli di base sono disponibili informazioni su quanto segue:  

- Esigenze dell'infrastruttura IT di Contoso
- Networking
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gestione di dispositivi mobili
- Protezione delle informazioni
- Riepilogo della sicurezza Microsoft 365 Enterprise
- Team per un progetto top secret
- Sito di SharePoint Online per risorse digitali altamente riservate

Per informazioni sulla pianificazione di un aggiornamento, è consigliabile iniziare con [Introduzione all'aggiornamento di Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Obiettivi aziendali di Contoso per Teams

Per eseguire la migrazione degli utenti locali a Teams per la comunicazione, la collaborazione e la voce unificate, Contoso ha deciso i seguenti obiettivi aziendali:

- Abilitazione di Teams 

  Il team unificato di comunicazione e collaborazione di Contoso ha abilitato Teams con i criteri corretti per governare e abilitare la collaborazione interna ed esterna sicura. 

- Aggiornamento da Skype for Business a Teams 

  Skype for Business è stato ampiamente distribuito all'interno di Contoso. Con l'esigenza di spostare i sistemi legacy, Contoso ha deciso di aggiornare i loro utenti Skype for Business a Teams. Per altre informazioni, vedere [Case study contoso: piano di aggiornamento di Teams](voice-case-study-migration-plan.md).

- Sistema telefonico  

  Skype for Business con voIP aziendale sono stati ampiamente distribuiti all'interno di Contoso. Con la necessità di spostare i sistemi legacy che erano l'hop successivo per i server di mediazione, Contoso ha migrato i loro utenti voIP aziendale Skype for Business a Sistema telefonico. I siti Contoso usavano il piano per le chiamate Microsoft, il routing diretto del sistema telefonico o una combinazione di entrambi. Per altre informazioni, vedere [Case study di Contoso: Sistema telefonico](voice-case-study-phone-system.md).

- Instradamento basato sulla posizione 

  Con le sedi degli uffici nei paesi regolamentati dalla telefonia, Contoso doveva ricreare il routing Location-Based presente in Skype for Business nella distribuzione del sistema telefonico. Per altre informazioni, vedere [Case study di Contoso: Location-Based Routing](voice-case-study-location-based-routing.md).

- Chiamate di emergenza 

  Dove è stato implementato il routing diretto, Contoso configura le chiamate di emergenza con terze parti approvate. Per altre informazioni, vedere [Case study contoso: Chiamate di emergenza](voice-case-study-emergency-calling.md).

- Audioconferenza 

  Contoso configura i numeri dei servizi di audioconferenza ospitati nel proprio trunk SIP al provider PSTN. Per ulteriori informazioni, vedi [Case study di Contoso: Audioconferenza](voice-case-study-audio-conferencing.md). 

- Ottimizzazione multimediale locale 

  Contoso ha approfittato di Ottimizzazione multimediale locale in posizioni in cui aveva un unico trunk di route dirette a Microsoft Phone System che è stato sfruttato dai siti remoti. Per ulteriori informazioni, vedi [Pianificare Ottimizzazione multimediale locale](direct-routing-media-optimization.md) e [Configurare l'ottimizzazione multimediale locale](direct-routing-media-optimization-configure.md).

- Operatori automatici e code di chiamata

  Come risultato di Screenshot-19, Contoso voleva fornire supporto receptionist mentre il loro personale lavorava in remoto. Contoso ha usato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono del receptionist. Per altre informazioni, vedere case [study contoso: Operatori automatici e code di chiamata](voice-case-study-call-queues.md).
