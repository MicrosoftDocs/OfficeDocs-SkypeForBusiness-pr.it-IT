---
title: Soluzioni di telefonia Microsoft
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 'Informazioni sulle soluzioni di telefonia Microsoft: Sistema telefonico (Private Branch Exchange - PBX) e opzioni di connettività PSTN (Piani di chiamata e routing diretto).'
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 4fa6b04fba5b9dbea30cfeeb9e347cf542f07d38
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110592"
---
# <a name="microsoft-telephony-solutions"></a>Soluzioni di telefonia Microsoft

Microsoft supporta diverse opzioni durante l'inizio del percorso verso Teams nel cloud Microsoft. Questo articolo consente di decidere quale soluzione di telefonia Microsoft (Sistema telefonico nel cloud o VoIP aziendale locale) è ideale per gli utenti dell'organizzazione e come l'organizzazione può connettersi alla rete PSTN (Public Switched Telephone Network).

È consigliabile utilizzare questo articolo insieme al diagramma tecnico associato, che fornisce un supporto visivo per prendere la decisione giusta per l'organizzazione:

- [Soluzioni di telefonia Microsoft - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluzioni di telefonia Microsoft - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opzioni PBX (Private Branch Exchange)

### <a name="phone-system-microsoft-365-or-office-365"></a>Sistema telefonico (Microsoft 365 o Office 365)
  
Sistema telefonico è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud di Microsoft 365 o Office 365 con Microsoft Teams e/o Skype for Business online.

Sistema telefonico funziona con i client Teams o Skype for Business Online e i dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente fornito da Microsoft 365 o Office 365 e strettamente integrato nell'esperienza di produttività cloud dell'azienda. Per connettere Il sistema telefonico alla rete PSTN (Public Switched Telephone Network), è possibile scegliere il Piano chiamate di Microsoft o il proprio operatore di telefonia.

Per ulteriori informazioni, vedere [What is Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>VoIP aziendale (Skype for Business Server)

VoIP aziendale è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) in Skype for Business Server locale. Questa opzione di Skype for Business può essere connessa solo alla rete telefonica a commutazione pubblica utilizzando il proprio operatore di telefonia.

Per ulteriori informazioni, vedere [Plan for VoIP aziendale in Skype for Business Server.](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connessione alle opzioni PSTN (Public Switched Telephone Network)

È possibile scegliere di connettersi alla rete PSTN (Public Switched Telephone Network) tramite:

- Uso di Microsoft Calling Plan in Microsoft 365 o Office 365 
- Connessione dell'operatore telefonico

### <a name="calling-plan-microsoft-365-or-office-365"></a>Piano di chiamata (Microsoft 365 o Office 365)

Questa opzione connette Microsoft 365 o Office 365 Phone System alla rete PSTN (Public Switched Telephone Network) per abilitare le chiamate a telefoni fissi e cellulari in tutto il mondo. Con Piano di chiamata, Microsoft è l'operatore PSTN.

Per ulteriori informazioni, vedere [Piani di chiamata per Microsoft 365 o Office 365.](/MicrosoftTeams/calling-plans-for-office-365)

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Connettere il proprio operatore di telefonia (Microsoft 365 o Office 365 e Skype for Business in locale)

Questa opzione connette sistema telefonico in Microsoft 365 o Office 365 o VoIP aziendale system in Skype for Business locale alla rete di telefonia. Questa opzione richiede un session border controller (SBC) supportato. In alcuni casi, questa opzione potrebbe richiedere software Microsoft aggiuntivo distribuito in locale.

## <a name="which-solution-is-right-for-your-organization"></a>Qual è la soluzione giusta per l'organizzazione?

È possibile scegliere una soluzione all-in-the-cloud, una soluzione connect-your-own-carrier o una combinazione tra operatori all-in-the-cloud e di terze parti:

- Sistema telefonico con piano di chiamata (tutto nel cloud)

- Sistema telefonico con operatore proprio tramite instradamento diretto

- Sistema telefonico con operatore personale tramite Skype for Business Server O Cloud Connector Edition

- VoIP aziendale in Skype for Business Server con un proprio operatore

La soluzione scelta dipende dalle esigenze attuali e future, ad esempio:

- Indipendentemente dal fatto che si desideri, o sia necessario, conservare le funzionalità fornite dalla distribuzione locale.
- Quale client si desidera distribuire per gli utenti.
- Qual è il piano per lo spostamento delle persone nel cloud.
- Sia che sia necessario interagire con IBX di terze parti e altre apparecchiature telefoniche.

Considerare le domande seguenti per determinare la soluzione migliore per l'organizzazione:

- Si dispone di una distribuzione di Skype for Business Server esistente?
- Gli utenti sono ospitati in Skype for Business in locale, nel cloud in Skype for Business online o in entrambi i casi? 
- Si desidera spostare gli utenti locali nel cloud?
- Il piano per chiamate PSTN di Microsoft è disponibile nella propria area geografica?
- Si desidera o si desidera mantenere l'attuale operatore telefonico?  Ad esempio, è necessario mantenere il vettore corrente a causa di un contratto esistente?
- Si dispone di un pbx legacy locale che si desidera o si desidera mantenere?
- Il pbx legacy corrente offre funzionalità uniche fondamentali per l'azienda?
- Alcuni o tutti gli utenti richiedono funzionalità attualmente non disponibili in Sistema telefonico?

Tenere presente quanto segue:

- Tutte e quattro le opzioni possono coesistere tra loro nel caso in cui sia necessario progettare una soluzione per un ambiente complesso o gestire la migrazione in più passaggi.
- Il sistema telefonico con operatore personale tramite Skype for Business Server o Cloud Connector Edition può essere distribuito solo con Skype for Business Server o Cloud Connector. La coesistenza di Skype for Business Server e Cloud Connector non è supportata in una singola società.

## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con piano di chiamata


Sistema telefonico con piano di chiamata è un'opzione all-in-the-cloud per gli utenti di Teams o Skype for Business Online, come illustrato nel diagramma seguente:

![Sistema telefonico con piano di chiamata](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema telefonico Microsoft con piani di chiamata nazionali o internazionali aggiunti che consentono di chiamare i telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza). 
- Poiché il piano di chiamata PSTN funziona da Microsoft 365 o Office 365, questa opzione non richiede la distribuzione o la manutenzione di alcuna distribuzione locale.
- I clienti possono connettere un SBC supportato tramite direct routing per l'interoperabilità con PBX di terze parti, dispositivi analogici e altre apparecchiature telefoniche di terze parti supportate dal sistema SBC.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo*                            | No  |
| Richiede la distribuzione e la manutenzione di un session border controller (SBC) supportato | No |
| Richiede un contratto con un operatore di terze parti      | No   |
| Richiede la distribuzione e la manutenzione di Skype for Business Server o Cloud Connector Edition | No |

\*Per ulteriori informazioni sui paesi in cui è disponibile il Piano per le chiamate, vedere Disponibilità di audioconferenza e piani di chiamata per paese e [area geografica.](/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)


Se si risponde sì alle domande seguenti, questa è la soluzione giusta:

- Piano di chiamata è disponibile nella tua area geografica.
- Non è necessario conservare l'operatore PSTN corrente.
- Si desidera utilizzare l'accesso gestito da Microsoft alla rete PSTN (Public Switched Telephone Network).
- Non si desidera gestire i Session Border Controller da soli.
- Teams e/o Skype for Business online dispone di tutte le funzionalità necessarie per l'organizzazione.

Per ulteriori informazioni, vedere [What is Phone System in Microsoft 365 and Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) e Calling Plans for Microsoft [365 or Office 365](/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefonico con operatore proprio tramite instradamento diretto

Questa opzione offre a Microsoft Phone System nel cloud praticamente qualsiasi operatore di telefonia per gli utenti di Teams.

![Sistema telefonico con l'operatore tramite instradamento diretto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connetti il tuo SBC supportato a Microsoft Phone System direttamente senza bisogno di software locale aggiuntivo.  
- Usa praticamente qualsiasi operatore di telefonia con Microsoft Phone System.
- Può essere configurato e gestito dai clienti o dal tuo operatore o partner (chiedi se il tuo operatore o partner fornisce questa opzione).
- Configurare l'interoperabilità tra le apparecchiature telefoniche, ad esempio un PBX di terze parti e dispositivi analogici, e Microsoft Phone System.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la manutenzione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un operatore di terze parti*      | Sì   |
| Richiede la distribuzione e la manutenzione di Skype for Business Server o Cloud Connector Edition | No |

\* A meno che non venga distribuito come opzione per fornire la connessione a SISTEMI PBX di terze parti, dispositivi analogici o altre apparecchiature telefoniche per gli utenti che sono in sistema telefonico con piani di chiamata.

Se si risponde sì alle domande seguenti, questa è la soluzione giusta:

- Si desidera utilizzare Teams con Sistema telefonico.
- È necessario conservare l'operatore PSTN corrente.
- Si desidera combinare il routing, alcune chiamate vengono effettuate tramite Piani di chiamata, altre tramite l'operatore
- Devi interagire con SISTEMI DI TERZE PARTI e/o attrezzature come i pager sovraccarico, i dispositivi analogici
- Teams dispone di tutte le funzionalità necessarie per l'organizzazione.

Per ulteriori informazioni, vedere [What is Phone System in Microsoft 365 and Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) e Plan Direct [Routing.](/MicrosoftTeams/direct-routing-plan)


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefonico con operatore personale tramite Skype for Business Server O Cloud Connector Edition

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

Questa opzione offre a Microsoft Phone System nel cloud la connettività a una rete di telefonia locale per gli utenti di Skype for Business Online.

![Sistema telefonico con l'operatore tramite Skype for Business Server O Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connetti il tuo SBC supportato a Microsoft Phone System tramite Skype for Business Server o Skype for Business Cloud Connector Edition distribuito in locale. 
- Usa praticamente qualsiasi operatore di telefonia con Microsoft Phone System. 
- Se si dispone già di Skype for Business Server in locale, è possibile sfruttarlo.  in caso contrario, è possibile distribuire una versione più leggera: Cloud Connector Edition.


| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la manutenzione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un operatore di terze parti      | Sì   |
| Richiede la distribuzione e la manutenzione di Skype for Business Server o Cloud Connector Edition | Sì |



Se si risponde sì alle domande seguenti, questa è la soluzione giusta:

- Si desidera usare Skype for Business online per gli utenti.
- Il piano per chiamate PSTN non è disponibile nella propria area geografica.
- È necessario conservare l'operatore PSTN corrente.

Per ulteriori informazioni, vedere What [is Phone System in Microsoft 365 and Office 365,](/MicrosoftTeams/what-is-phone-system-in-office-365)Skype for Business Server [2019](../../SfBServer2019/skype-for-business-server-2019.yml)e [Plan for Skype for Business Cloud Connector Edition.](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)

Suggerimento: quando le condizioni aziendali cambiano, ad esempio non è più necessario conservare il gestore PSTN, è consigliabile passare a Microsoft Teams utilizzando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle funzionalità più recenti rilasciate da Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>VoIP aziendale in Skype for Business Server con un proprio operatore

Questa opzione VoIP aziendale locale con connettività a una rete di telefonia locale per gli utenti locali di Skype for Business.

![VoIP aziendale in Skype for Business Server con un proprio operatore](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connettere il proprio SBC supportato VoIP aziendale sistema in Skype for Business server locale.
- Utilizzare se è necessaria la sopravvivenza locale.
- Usa praticamente qualsiasi operatore di telefonia con Microsoft Phone System. 
- Opzione più complessa da distribuire e gestire.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | No |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la manutenzione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un operatore di terze parti      | Sì   |
| Richiede la distribuzione e la manutenzione di Skype for Business Server | Sì |

Per ulteriori informazioni, vedere [Plan for VoIP aziendale in Skype for Business Server.](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

Suggerimento: quando le condizioni aziendali cambiano, ad esempio non è più necessario conservare il gestore PSTN, è consigliabile passare a Microsoft Teams utilizzando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle funzionalità più recenti rilasciate da Microsoft