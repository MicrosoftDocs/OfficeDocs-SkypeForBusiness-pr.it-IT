---
title: Soluzioni telefoniche Microsoft
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
description: Vengono descritte le soluzioni di telefonia Microsoft.
ms.openlocfilehash: c317079284c43f2578141827409655903982b79e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221326"
---
# <a name="microsoft-telephony-solutions"></a>Soluzioni telefoniche Microsoft

Microsoft supporta diverse opzioni quando si inizia il viaggio a squadre nel cloud Microsoft. In questo articolo vengono fornite informazioni utili per decidere quale soluzione di telefonia Microsoft (sistema telefonico nel cloud o VoIP aziendale) sia corretta per gli utenti dell'organizzazione e in che modo l'organizzazione può connettersi alla rete PSTN (Public Switched Telephone Network). 

È consigliabile utilizzare questo articolo insieme al diagramma tecnico associato, che fornisce un supporto visivo per prendere la decisione giusta per la propria organizzazione:

- [Soluzioni telefoniche Microsoft-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluzioni telefoniche Microsoft-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opzioni del PBX (Private Branch Exchange)

### <a name="phone-system-microsoft-365-or-office-365"></a>Sistema telefonico (Microsoft 365 o Office 365)
  
Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) in Microsoft 365 o Office 365 cloud con Microsoft teams e/o Skype for business online. 

Sistema telefonico compatibile con i team o con i client Skype for business online e con i dispositivi certificati. Il sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente recapitate da Microsoft 365 o Office 365 e strettamente integrate nell'esperienza di produttività cloud dell'azienda. Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network), è possibile scegliere il piano di chiamata di Microsoft o il proprio carrier di telefonia.

Per ulteriori informazioni, vedere [che cos'è il sistema telefonico in Microsoft 365 o Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>VoIP aziendale (Skype for Business Server)

VoIP aziendale è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) nel server Skype for business locale. Questa opzione può essere connessa solo alla rete telefonica pubblica commutata tramite il proprio gestore di telefonia. 

Per ulteriori informazioni, vedere [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connessione alle opzioni PSTN (Public Switched Telephone Network)

È possibile scegliere di connettersi alla rete PSTN (Public Switched Telephone Network) per:

- Utilizzo di Microsoft Calling Plan in Microsoft 365 o Office 365 
- Connessione di un gestore di telefonia personalizzato

### <a name="calling-plan-microsoft-365-or-office-365"></a>Piano per le chiamate (Microsoft 365 o Office 365)

Questa opzione consente di connettere il sistema telefonico Microsoft 365 o Office 365 alla rete PSTN (Public Switched Telephone Network) per abilitare le chiamate ai telefoni fissi e mobili di tutto il mondo. Con il piano di chiamata, Microsoft è il gestore PSTN.

Per ulteriori informazioni, vedere [Calling plans for Microsoft 365 or Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Connettere il proprio carrier di telefonia (Microsoft 365 o Office 365 e Skype for business in locale)

Questa opzione consente di connettere il sistema telefonico in Microsoft 365 o Office 365 o il sistema VoIP aziendale in Skype for business in locale alla rete di telefonia. Questa opzione richiede un session border controller (SBC) supportato. In alcuni casi, questa opzione può richiedere la distribuzione in locale di ulteriori software Microsoft.

## <a name="which-solution-is-right-for-your-organization"></a>Quale soluzione è adatta alla propria organizzazione?

È possibile scegliere una soluzione all-in-the-cloud, una soluzione Connect-your-own-Carrier o una combinazione tra i vettori all-in-the-cloud e di terze parti:

- Sistema telefonico con piano per chiamate (tutto nel cloud)

- Sistema telefonico con portante privato tramite routing diretto

- Sistema telefonico con supporto proprio tramite Skype for Business Server o Cloud Connector Edition

- VoIP aziendale in Skype for Business Server con supporto personale

La soluzione scelta dipende dalle esigenze correnti e future, ad esempio:

- Se si desidera, o sono necessari,-per mantenere la funzionalità fornita dalla distribuzione locale.
- Il client che si desidera distribuire per gli utenti.
- Che cosa è il piano per spostare le persone nel cloud.
- Se è necessario interagire con i sistemi PBX di terze parti e altre apparecchiature di telefonia.

Tenere presenti le domande seguenti per determinare la soluzione migliore per l'organizzazione:

- Si dispone di una distribuzione di Skype for Business Server esistente?
- Gli utenti sono ospitati in Skype for business in locale, nel cloud su Skype for business online o in entrambi i siti? 
- Si desidera spostare gli utenti locali nel cloud?
- Il piano per le chiamate PSTN di Microsoft è disponibile nella propria area geografica?
- Si desidera o si ha la necessità di mantenere l'attuale operatore di telefonia?  Ad esempio, è necessario mantenere il vettore corrente a causa di un contratto esistente?
- Si dispone di un PBX legacy locale esistente che si desidera o è necessario mantenere?
- Il sistema PBX legacy corrente offre funzionalità esclusive che sono fondamentali per la propria azienda?
- Qualsiasi utente o tutti gli utenti devono disporre di funzionalità non attualmente disponibili nel sistema telefonico?

Tenere presente quanto segue:

- Tutte le quattro opzioni possono coesistere tra loro nel caso in cui sia necessario progettare una soluzione per un ambiente complesso o gestire la migrazione in più passaggi.
- Il sistema telefonico con il proprio operatore tramite Skype for Business Server o Cloud Connector Edition può essere distribuito solo con Skype for Business Server o Cloud Connector. La coesistenza di Skype for Business Server e Cloud Connector non è supportata in una singola società.

## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con piano per chiamate


Il sistema telefonico con il piano di chiamata è un'opzione all-in-the-cloud per gli utenti di team o Skype for business online, come illustrato nel diagramma seguente:

![Sistema telefonico con piano per chiamate](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema telefonico Microsoft con piani di chiamata nazionali o internazionali aggiunti che consentono la chiamata ai telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza). 
- Poiché il piano per le chiamate PSTN opera in Microsoft 365 o Office 365, questa opzione non richiede la distribuzione o la manutenzione di una distribuzione locale.
- I clienti possono connettere un SBC supportato tramite il routing diretto per l'interoperabilità con PBX di terze parti, dispositivi analogici e altre apparecchiature di telefonia di terze parti supportate da SBC.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo *                            | No  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | No |
| Richiede contratto con corriere di terze parti      | No   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\*Per ulteriori informazioni sui paesi in cui è disponibile il piano per le chiamate, vedere [disponibilità del paese e delle aree geografiche per audioconferenza e piani di chiamata](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Se si risponde Sì alle domande seguenti, questa è la soluzione ideale per l'utente:

- Il piano di chiamata è disponibile nella propria area geografica.
- Non è necessario mantenere il gestore PSTN corrente.
- Si desidera utilizzare l'accesso gestito da Microsoft alla rete PSTN (Public Switched Telephone Network).
- Non si desidera gestire i controlli Border Session da soli.
- Teams e/o Skype for business online include tutte le caratteristiche richieste dall'organizzazione.

Per ulteriori informazioni, vedere [che cos'è il sistema telefonico in microsoft 365 e office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) e [piani di chiamata per Microsoft 365 o Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefonico con portante privato tramite routing diretto

Questa opzione fornisce a Microsoft Phone System nel cloud praticamente qualsiasi operatore di telefonia per gli utenti di team.

![Sistema telefonico con il gestore tramite routing diretto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connettere il proprio SBC supportato a Microsoft Phone System direttamente senza bisogno di ulteriori software locali.  
- Utilizzare virtualmente qualsiasi operatore di telefonia con sistema telefonico Microsoft.
- Possono essere configurati e gestiti dai clienti o dal gestore o dal partner (Chiedi se il gestore o il partner fornisce questa opzione).
- Configurare l'interoperabilità tra le apparecchiature telefoniche, ad esempio i dispositivi PBX e analogici di terze parti, e il sistema telefonico Microsoft.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede contratto con corriere di terze parti *      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\*A meno che non venga distribuito come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature di telefonia per gli utenti che si trovano nel sistema telefonico con piani di chiamata.

Se si risponde Sì alle domande seguenti, questa è la soluzione ideale per l'utente:

- Si desidera utilizzare Team con sistema telefonico.
- È necessario mantenere l'operatore PSTN corrente.
- Si vuole mescolare il routing, alcune chiamate vengono eseguite tramite piani di chiamata, alcune tramite il proprio operatore
- È necessario interoperare con sistemi PBX e/o apparecchiature di terze parti, ad esempio, dispositivi analogici
- I team dispongono di tutte le funzionalità necessarie per l'organizzazione.

Per ulteriori informazioni, vedere [che cos'è il sistema telefonico in Microsoft 365 e Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) e [pianificare il routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefonico con supporto proprio tramite Skype for Business Server o Cloud Connector Edition

Questa opzione consente a Microsoft Phone System nel cloud di connettersi a una rete di telefonia locale per gli utenti di Skype for business online.

![Sistema telefonico con il gestore tramite Skype for Business Server o Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connettere il proprio SBC supportato a Microsoft Phone System tramite Skype for Business Server o Skype for Business Cloud Connector Edition distribuito in locale. 
- Utilizzare virtualmente qualsiasi operatore di telefonia con sistema telefonico Microsoft. 
- Se si dispone già di Skype for Business Server in locale, è possibile sfruttarlo;  in caso contrario, è possibile distribuire una versione più leggera – Cloud Connector Edition.


| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede contratto con corriere di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | Sì |



Se si risponde Sì alle domande seguenti, questa è la soluzione ideale per l'utente:

- Si desidera utilizzare Skype for business online per gli utenti.
- Il piano per le chiamate PSTN non è disponibile nella propria area geografica.
- È necessario mantenere l'operatore PSTN corrente.

Per ulteriori informazioni, vedere [che cos'è il sistema telefonico in Microsoft 365 e Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)e [Plan for Skype for Business Cloud Connector Edition](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Suggerimento: quando si modificano le condizioni aziendali, ad esempio, non è più necessario mantenere il gestore PSTN, è consigliabile passare a Microsoft teams utilizzando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Accedere alle funzionalità più recenti rilasciate da Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>VoIP aziendale in Skype for Business Server con supporto personale

Questa opzione consente a VoIP aziendale di connettersi a una rete di telefonia locale per gli utenti di Skype for business in locale.

![VoIP aziendale in Skype for Business Server con supporto personale](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connettere il proprio SBC supportato a Enterprise Voice System nel server locale di Skype for business.
- Utilizzare se si necessita di una sopravvivenza locale.
- Utilizzare virtualmente qualsiasi operatore di telefonia con sistema telefonico Microsoft. 
- Opzione più complessa per la distribuzione e la manutenzione.

| Requisiti dell'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede una connessione ininterrotta a Microsoft 365 o Office 365 | No |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un session border controller (SBC) supportato | Sì |
| Richiede contratto con corriere di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server | Sì |

Per ulteriori informazioni, vedere [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Suggerimento: quando si modificano le condizioni aziendali, ad esempio, non è più necessario mantenere il gestore PSTN, è consigliabile passare a Microsoft teams utilizzando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Accedere alle funzionalità più recenti rilasciate da Microsoft
