---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701224"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Case study contoso: Panoramica della migrazione vocale di Teams

Questo articolo presenta un case study sul modo in cui una multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione.

Contoso ha distribuito Microsoft 365 Enterprise e ha definito le principali decisioni di progettazione e dettagli di implementazione per: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione di dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e Audioconferenza.  

Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce. Per informazioni generali su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Microsoft, vedere tutti gli articoli di base a partire dalla panoramica [del case study di Contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Negli articoli principali sono disponibili le informazioni seguenti:  

- Necessità dell'infrastruttura IT di Contoso
- Rete
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gestione di dispositivi mobili
- Protezione delle informazioni
- Riepilogo della sicurezza di Microsoft 365 Enterprise
- Team per un progetto top-secret
- Sito di SharePoint Online per risorse digitali altamente riservate

Per informazioni sulla pianificazione di un aggiornamento, è possibile iniziare con l'aggiornamento [a Microsoft Teams.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Obiettivi aziendali di Contoso per Teams

Per eseguire la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce, Contoso ha deciso i seguenti obiettivi aziendali:

- Abilitazione di Teams 

  Il team di comunicazione e collaborazione unificato di Contoso ha abilitato Teams con i criteri corretti per governare e consentire la collaborazione interna ed esterna sicura. 

- Aggiornamento da Skype for Business a Teams 

  Skype for Business è stato ampiamente distribuito all'interno di Contoso. Con l'esigenza di spostare i sistemi legacy, Contoso ha deciso di aggiornare gli utenti di Skype for Business a Teams. Per altre informazioni, vedere il case [study contoso: piano di aggiornamento di Teams.](voice-case-study-migration-plan.md)

- Phone System  

  Skype for Business con voce aziendale è stato ampiamente distribuito all'interno di Contoso. Con la necessità di spostare i sistemi legacy che rappresentavano l'hop successivo per i loro mediation server, Contoso ha eseguito la migrazione dei loro utenti VoIP aziendale di Skype for Business al Sistema telefonico. I siti Contoso usava il Piano per chiamate Microsoft, l'instradamento diretto del sistema telefonico o una combinazione di entrambi. Per altre informazioni, vedere il [case study di Contoso: Sistema telefonico.](voice-case-study-phone-system.md)

- Instradamento basato sulla posizione 

  Con le sedi di uffici in paesi regolamentati dalla telefonia, Contoso ha bisogno di ricreare il routing Location-Based presente in Skype for Business nella distribuzione del Sistema telefonico. Per altre informazioni, vedere il [case study contoso: Location-Based routing.](voice-case-study-location-based-routing.md)

- Chiamate di emergenza 

  Dove è stato implementato il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate. Per ulteriori informazioni, consulta il [case study di Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)

- Audioconferenza 

  Contoso ha configurato i numeri dei servizi di audioconferenza ospitati nel trunk SIP al proprio provider PSTN. Per altre informazioni, vedere il [case study di Contoso: Audioconferenza.](voice-case-study-audio-conferencing.md) 

- Ottimizzazione degli elementi multimediali locali 

  Contoso ha sfruttato l'Ottimizzazione supporto locale in posizioni in cui aveva un trunk di percorso diretto al Sistema telefonico Microsoft, sfruttato dai siti remoti. Per altre informazioni, vedere [Pianificare l'ottimizzazione degli elementi](direct-routing-media-optimization.md) multimediali locali e Configurare [l'ottimizzazione degli elementi multimediali locali.](direct-routing-media-optimization-configure.md)

- Operatori automatici e code di chiamata

  In seguito al lavoro di Covid-19, Contoso ha voluto fornire assistenza all'addetto della reception mentre il personale lavora da remoto. Contoso ha utilizzato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla reception. Per ulteriori informazioni, consulta il [case study di Contoso: Operatori automatici e Code di chiamata.](voice-case-study-call-queues.md)  


