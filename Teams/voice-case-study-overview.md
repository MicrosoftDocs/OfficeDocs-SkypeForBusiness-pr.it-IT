---
title: Case study di Teams voice Contoso
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
description: Case study vocale di Teams per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097492"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Case study contoso: Panoramica della migrazione vocale di Teams

Questo articolo presenta un case study che illustra come una multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione.

Contoso ha distribuito Microsoft 365 Enterprise e ha indirizzato le principali decisioni di progettazione e i dettagli di implementazione per i seguenti elementi: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione dei dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e Audioconferenza.  

Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce. Per informazioni di base su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Di Microsoft, vedere tutti gli articoli di base che iniziano con la panoramica [del case study di Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Negli articoli principali sono disponibili informazioni su quanto segue:  

- Esigenze dell'infrastruttura IT di Contoso
- Rete
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gestione di dispositivi mobili
- Protezione delle informazioni
- Riepilogo della sicurezza di Microsoft 365 Enterprise
- Team per un progetto top secret
- Sito di SharePoint Online per risorse digitali altamente riservate

Per informazioni sulla pianificazione di un aggiornamento, è necessario iniziare con Introduzione [all'aggiornamento di Microsoft Teams.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Obiettivi aziendali contoso per Teams

Per eseguire la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce, Contoso ha deciso gli obiettivi aziendali seguenti:

- Abilitazione di Teams 

  Il team di comunicazione e collaborazione unificato di Contoso ha abilitato Teams con i criteri corretti per governare e abilitare la collaborazione interna ed esterna sicura. 

- Aggiornamento da Skype for Business a Teams 

  Skype for Business è stato ampiamente distribuito all'interno di Contoso. Con la necessità di allontanare i sistemi legacy, Contoso ha deciso di aggiornare gli utenti skype for business a Teams. Per altre informazioni, vedere Case [study contoso: Piano di aggiornamento di Teams.](voice-case-study-migration-plan.md)

- Sistema telefonico  

  Skype for Business con voIP aziendale è stato ampiamente distribuito all'interno di Contoso. Con la necessità di allontanare i sistemi legacy che rappresentavano l'hop successivo per i server di mediazione, Contoso ha eseguito la migrazione degli utenti voIP aziendali Skype for Business a Sistema telefonico. I siti contoso hanno usato Microsoft Calling Plan, Phone System Direct Routing o una combinazione di entrambi. Per altre informazioni, vedere Caso [di studio contoso: Sistema telefonico](voice-case-study-phone-system.md).

- Instradamento basato sulla posizione 

  Con le sedi degli uffici nei paesi regolamentati dalla telefonia, Contoso doveva ricreare il routing Location-Based che era presente in Skype for Business nella distribuzione del sistema telefonico. Per altre informazioni, vedere [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md).

- Chiamate di emergenza 

  Dove è stato implementato Il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate. Per altre informazioni, vedere Caso [di studio Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)

- Audioconferenza 

  Contoso configura i numeri dei servizi di audioconferenza ospitati nel trunk SIP al provider PSTN. Per altre informazioni, vedere Case [study contoso: Audioconferenza.](voice-case-study-audio-conferencing.md) 

- Ottimizzazione del supporto locale 

  Contoso ha sfruttato l'Ottimizzazione multimediale locale nelle posizioni in cui aveva un unico trunk di percorso diretto a Microsoft Phone System che è stato sfruttato da siti remoti. Per altre informazioni, vedere [Pianificare l'ottimizzazione dei supporti locali](direct-routing-media-optimization.md) [e Configurare l'ottimizzazione dei supporti multimediali locali.](direct-routing-media-optimization-configure.md)

- Operatori automatici e code di chiamata

  Come risultato di Covid-19, Contoso voleva fornire supporto per l'addetto alla reception mentre il personale stava lavorando in remoto. Contoso ha usato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla ricezione. Per altre informazioni, vedere [Case study contoso: Operatori automatici e code di chiamata.](voice-case-study-call-queues.md)