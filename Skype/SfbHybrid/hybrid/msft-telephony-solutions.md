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
description: 'Informazioni sulle soluzioni di telefonia Di Microsoft: Sistema telefonico (Private Branch Exchange - PBX) e opzioni di connettività PSTN (Piani di chiamata e instradamento diretto).'
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 3f5e4f0cf0cb027ed0c18b98c85b123634687a77
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878540"
---
# <a name="microsoft-telephony-solutions"></a>Soluzioni di telefonia Microsoft

Microsoft supporta diverse opzioni quando si inizia il percorso verso Teams nel cloud Microsoft. Questo articolo consente di decidere quale soluzione di telefonia Microsoft (Sistema telefonico nel cloud o VoIP aziendale locale) è ideale per gli utenti dell'organizzazione e come l'organizzazione può connettersi alla rete PSTN (Public Switched Telephone Network).

È consigliabile utilizzare questo articolo insieme al diagramma tecnico associato, che fornisce un aiuto visivo per prendere la decisione giusta per l'organizzazione:

- [Soluzioni di telefonia Microsoft - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluzioni di telefonia Microsoft - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opzioni PBX (Private Branch Exchange)

### <a name="phone-system-microsoft-365-or-office-365"></a>Sistema telefonico (Microsoft 365 o Office 365)
  
Sistema telefonico è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud di Microsoft 365 o Office 365 con Microsoft Teams e/o Skype for Business online.

Il sistema telefonico funziona con i client Teams o Skype for Business online e i dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente fornito da Microsoft 365 o Office 365 e strettamente integrato nell'esperienza di produttività cloud aziendale. Per connettere Sistema telefonico alla rete PSTN (Public Switched Telephone Network), è possibile scegliere il Piano per chiamate di Microsoft o il proprio gestore telefonico.

Per altre informazioni, vedere [Che cos'è Sistema telefonico in Microsoft 365 o Office 365.](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)

### <a name="enterprise-voice-skype-for-business-server"></a>VoIP aziendale (Skype for Business Server)

VoIP aziendale è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) in Skype for Business Server locale. Questa opzione di Skype for Business può essere connessa solo alla rete telefonica a commutazione pubblica utilizzando il proprio gestore telefonico.

Per ulteriori informazioni, vedere [Pianificare VoIP aziendale in Skype for Business Server.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connessione alle opzioni PSTN (Public Switched Telephone Network)

È possibile scegliere di connettersi alla rete PSTN (Public Switched Telephone Network) tramite:

- Uso di Microsoft Calling Plan in Microsoft 365 o Office 365 
- Connessione del proprio gestore telefonico

### <a name="calling-plan-microsoft-365-or-office-365"></a>Piano di chiamata (Microsoft 365 o Office 365)

Questa opzione consente di connettere Il sistema telefonico di Microsoft 365 o Office 365 alla rete PSTN (Public Switched Telephone Network) per abilitare le chiamate verso telefoni fissi e cellulari in tutto il mondo. Con Piano per chiamate, Microsoft è il gestore PSTN.

Per ulteriori informazioni, vedere [Piani di chiamata per Microsoft 365 o Office 365.](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Connettere il proprio gestore telefonico (Microsoft 365 o Office 365 e Skype for Business in locale)

Questa opzione consente di connettere sistema telefonico in Microsoft 365 o Office 365 o VoIP aziendale in Skype for Business locale alla rete telefonica. Questa opzione richiede un SBC (Session Border Controller) supportato. In alcuni casi, questa opzione potrebbe richiedere software Microsoft aggiuntivo distribuito in locale.

## <a name="which-solution-is-right-for-your-organization"></a>Qual è la soluzione più ideale per l'organizzazione?

È possibile scegliere una soluzione all-in-the-cloud, una soluzione connect-your-own-carrier o una combinazione tra operatori all-in-the-cloud e di terze parti:

- Sistema telefonico con Piano di chiamata (tutto nel cloud)

- Sistema telefonico con gestore telefonico tramite instradamento diretto

- Sistema telefonico con gestore telefonico tramite Skype for Business Server O Cloud Connector Edition

- VoIP aziendale in Skype for Business Server con gestore telefonico

La soluzione scelta dipende dalle esigenze attuali e future, ad esempio:

- Indipendentemente dal fatto che si desideri o sia necessario mantenere le funzionalità fornite dalla distribuzione locale.
- Quale client si desidera distribuire per gli utenti.
- Qual è il piano per spostare le persone nel cloud.
- Se è necessario interagire con i DISPOSITIVI DI TERZE PARTI e altre apparecchiature telefoniche.

Considerare le domande seguenti per determinare la soluzione migliore per l'organizzazione:

- Si dispone di una distribuzione di Skype for Business Server esistente?
- Gli utenti sono ospitati in Skype for Business in locale, nel cloud su Skype for Business online o entrambi? 
- Si desidera spostare gli utenti locali nel cloud?
- Il Piano per le chiamate PSTN di Microsoft è disponibile nella propria area geografica?
- Si desidera o è necessario mantenere il gestore telefonico corrente?  Ad esempio, è necessario mantenere il vettore corrente a causa di un contratto esistente?
- Si dispone di un PBX legacy locale che si desidera o si desidera mantenere?
- Il pbx legacy corrente offre funzionalità uniche fondamentali per l'azienda?
- Alcuni o tutti gli utenti richiedono funzionalità attualmente non disponibili in Sistema telefonico?

Tenere presente quanto segue:

- Tutte e quattro le opzioni possono coesistere tra loro nel caso in cui sia necessario progettare una soluzione per un ambiente complesso o gestire la migrazione in più passaggi.
- Il sistema telefonico con gestore telefonico tramite Skype for Business Server o Cloud Connector Edition può essere distribuito solo con Skype for Business Server o Cloud Connector. La coesistenza di Skype for Business Server e Cloud Connector non è supportata in una singola società.

## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con piano di chiamata


Sistema telefonico con Piano di chiamata è un'opzione all-in-the-cloud per gli utenti di Teams o Skype for Business online, come illustrato nel diagramma seguente:

![Sistema telefonico con piano di chiamata](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema telefonico Microsoft con piani per chiamate nazionali o internazionali aggiunti che consentono di chiamare telefoni in tutto il mondo (a seconda del livello di servizio concesso in licenza). 
- Poiché il piano per chiamate PSTN opera al di fuori di Microsoft 365 o Office 365, questa opzione non richiede la distribuzione o la manutenzione di alcuna distribuzione locale.
- I clienti possono connettere un SBC supportato tramite instradamento diretto per l'interoperabilità con PBX di terze parti, dispositivi analogici e altre apparecchiature telefoniche di terze parti supportate dal controller SBC.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione senza interruzioni a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo*                            | No  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | No |
| Richiede un contratto con un gestore telefonico di terze parti      | No   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\*Per ulteriori informazioni sui paesi in cui è disponibile il Piano per chiamate, vedere Disponibilità di Audioconferenza e Piani di chiamata per paese [e area geografica.](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)


Se si risponde sì alle domande seguenti, questa è la soluzione più corretta:

- Piano di chiamata è disponibile nella tua area geografica.
- Non è necessario conservare il gestore PSTN corrente.
- Si desidera utilizzare l'accesso gestito da Microsoft alla rete PSTN (Public Switched Telephone Network).
- Non si desidera gestire i session border controller da soli.
- Teams e/o Skype for Business online hanno tutte le funzionalità necessarie per l'organizzazione.

Per altre informazioni, vedere Che cos'è Sistema telefonico [in Microsoft 365 e Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) e Piani di chiamata per [Microsoft 365 o Office 365.](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefonico con gestore telefonico tramite instradamento diretto

Questa opzione fornisce a Microsoft Phone System nel cloud praticamente qualsiasi operatore di telefonia per gli utenti di Teams.

![Sistema telefonico con il gestore telefonico tramite instradamento diretto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connetti il tuo SBC supportato direttamente a Microsoft Phone System senza bisogno di software locale aggiuntivo.  
- Utilizzare virtualmente qualsiasi operatore di telefonia con Microsoft Phone System.
- Può essere configurato e gestito dai clienti o dal gestore telefonico o dal partner (chiedere se il vettore o il partner fornisce questa opzione).
- Configurare l'interoperabilità tra le apparecchiature telefoniche, ad esempio un PBX di terze parti e dispositivi analogici, e Microsoft Phone System.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione senza interruzioni a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un operatore di terze parti*      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\* A meno che non venga distribuito come opzione per fornire la connessione a SISTEMI PBX di terze parti, dispositivi analogici o altre apparecchiature telefoniche per gli utenti che si consegnino a Sistema telefonico con Piani di chiamata.

Se si risponde sì alle domande seguenti, questa è la soluzione più corretta:

- Si desidera usare Teams con Sistema telefonico.
- È necessario conservare il gestore PSTN corrente.
- Si vuole combinare il routing, alcune chiamate sono in corso tramite Piani di chiamata, altre tramite il gestore telefonico
- È necessario interagire con sistemi PBX e/o attrezzature di terze parti come i pager sovraccarico e i dispositivi analogici
- Teams include tutte le funzionalità necessarie per l'organizzazione.

Per altre informazioni, vedere [Che cos'è Sistema telefonico in Microsoft 365 e Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) [e Pianificare l'instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefonico con gestore telefonico tramite Skype for Business Server O Cloud Connector Edition

> [!Important]
> Skype for Business online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Questa opzione fornisce a Microsoft Phone System nel cloud la connettività a una rete di telefonia locale per gli utenti di Skype for Business online.

![Sistema telefonico con il gestore telefonico tramite Skype for Business Server O Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connettere il proprio SBC supportato a Microsoft Phone System tramite Skype for Business Server o Skype for Business Cloud Connector Edition distribuito in locale. 
- Utilizzare virtualmente qualsiasi operatore di telefonia con Microsoft Phone System. 
- Se si dispone già di Skype for Business Server in locale, è possibile sfruttarlo;  In caso contrario, è possibile distribuire una versione più leggera: Cloud Connector Edition.


| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione senza interruzioni a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un gestore telefonico di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | Sì |



Se si risponde sì alle domande seguenti, questa è la soluzione più corretta:

- Si vuole usare Skype for Business online per gli utenti.
- Il Piano per chiamate PSTN non è disponibile nella propria area geografica.
- È necessario conservare il gestore PSTN corrente.

Per ulteriori informazioni, vedere Che cos'è Sistema telefonico [in Microsoft 365 e Office 365,](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) [Skype for Business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)e [Pianificare Skype for Business Cloud Connector Edition.](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)

Suggerimento: quando cambiano le condizioni aziendali, ad esempio non è più necessario conservare il gestore PSTN, prendere in considerazione la possibilità di passare a Microsoft Teams usando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle funzionalità più recenti rilasciate da Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>VoIP aziendale in Skype for Business Server con gestore telefonico

Questa opzione VoIP aziendale locale con connettività a una rete di telefonia locale per gli utenti locali di Skype for Business.

![VoIP aziendale in Skype for Business Server con gestore telefonico](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connettere il proprio SBC supportato VoIP aziendale sistema in Skype for Business server locale.
- Da usare se è necessaria la survivability locale.
- Utilizzare virtualmente qualsiasi operatore di telefonia con Microsoft Phone System. 
- Opzione più complessa per la distribuzione e la manutenzione.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione senza interruzioni a Microsoft 365 o Office 365 | No |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede un contratto con un gestore telefonico di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server | Sì |

Per ulteriori informazioni, vedere [Pianificare VoIP aziendale in Skype for Business Server.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)

Suggerimento: quando cambiano le condizioni aziendali, ad esempio non è più necessario conservare il gestore PSTN, prendere in considerazione la possibilità di passare a Microsoft Teams usando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle funzionalità più recenti rilasciate da Microsoft
