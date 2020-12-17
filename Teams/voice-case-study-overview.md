---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701224"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Case Study di Contoso: Panoramica della migrazione di teams Voice

Questo articolo introduce un caso di studio per il modo in cui una società multinazionale fittizia, contoso, ha implementato una soluzione per la voce teams per la propria organizzazione.

Contoso ha distribuito Microsoft 365 Enterprise e ha affrontato le principali decisioni di progettazione e i dettagli di implementazione per i seguenti servizi: networking, Identity, Windows 10 Enterprise, Office 365 ProPlus, gestione di dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for business a teams, sistema telefonico e servizi di audioconferenza.  

Questo articolo illustra in che modo Contoso ha migrato gli utenti locali ai team per la comunicazione, la collaborazione e la voce unificata. Per informazioni di base sul modo in cui Contoso ha accelerato la trasformazione digitale usando i servizi cloud di Microsoft, vedere tutti gli articoli principali a partire dalla [Panoramica del case study di Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Negli articoli principali sono disponibili le informazioni seguenti:  

- Esigenze dell'infrastruttura IT di contoso
- Networking
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gestione di dispositivi mobili
- Protezione delle informazioni
- Riepilogo della sicurezza aziendale di Microsoft 365
- Team per un progetto Top-Secret
- Sito di SharePoint Online per risorse digitali altamente riservate

Per informazioni sulla pianificazione di un aggiornamento, è consigliabile iniziare con [l'aggiornamento di Microsoft teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Obiettivi aziendali di Contoso per Teams

Per eseguire la migrazione degli utenti locali ai team per la comunicazione, la collaborazione e la voce unificata, Contoso ha deciso i seguenti obiettivi aziendali:

- Abilitazione Teams 

  Il team di comunicazione e collaborazione unificata di Contoso ha abilitato team con i criteri corretti per gestire e abilitare la collaborazione interna ed esterna sicura. 

- Aggiornamento da Skype for Business a Teams 

  Skype for business è stato ampiamente distribuito in contoso. Con la necessità di rimuovere i sistemi legacy, Contoso ha deciso di aggiornare gli utenti di Skype for business ai team. Per altre informazioni, vedere [Case Study di Contoso: piano di aggiornamento teams](voice-case-study-migration-plan.md).

- Sistema telefonico  

  Skype for business con Enterprise Voice è stato ampiamente distribuito in contoso. Con la necessità di spostare i sistemi legacy che sono stati l'hop successivo per i loro server di mediazione, Contoso ha migrato i loro utenti di Skype for Business VoIP per il sistema telefonico. I siti di Contoso hanno usato il piano di chiamata Microsoft, il routing diretto del sistema telefonico o una combinazione di entrambi. Per altre informazioni, Vedi [Case Study di Contoso: sistema telefonico](voice-case-study-phone-system.md).

- Instradamento basato sulla posizione 

  Con le posizioni di Office nei paesi regolamentati per la telefonia, Contoso ha avuto la necessità di ricreare il routing Location-Based presente in Skype for business nella distribuzione del sistema telefonico. Per altre informazioni, vedere [Case Study di Contoso: Location-Based routing](voice-case-study-location-based-routing.md).

- Chiamate di emergenza 

  Dove è stato implementato il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate. Per altre informazioni, Vedi [Case Study di Contoso: chiamate di emergenza](voice-case-study-emergency-calling.md).

- Audioconferenza 

  Contoso configura i numeri del servizio di audioconferenza ospitati nel trunk SIP nel proprio provider PSTN. Per altre informazioni, vedere [Case Study di Contoso:](voice-case-study-audio-conferencing.md)audioconferenza. 

- Ottimizzazione media locale 

  Contoso ha sfruttato l'ottimizzazione dei contenuti multimediali locali in posizioni in cui è stato eseguito un trunk diretto per il sistema telefonico Microsoft sfruttato da siti remoti. Per altre informazioni, vedere [pianificare l'ottimizzazione di elementi multimediali locali](direct-routing-media-optimization.md) e [configurare l'ottimizzazione dei contenuti multimediali locali](direct-routing-media-optimization-configure.md).

- Operatori automatici e code di chiamata

  Come risultato di Covid-19, Contoso ha voluto prestare supporto per il receptionist mentre il personale funzionava in remoto. Contoso ha usato gli operatori automatici e le code di chiamata per gestire le chiamate in arrivo al numero di telefono del receptionist. Per altre informazioni, vedere [Case Study di Contoso: operatori automatici e code di chiamata](voice-case-study-call-queues.md).  


