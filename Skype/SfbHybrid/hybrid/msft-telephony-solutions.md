---
title: Soluzioni per la telefonia Microsoft
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Descrive le soluzioni di telefonia Microsoft.
ms.openlocfilehash: 57d1abe69bc0513fa015543e8440e9d9f778b78c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185441"
---
# <a name="microsoft-telephony-solutions"></a>Soluzioni per la telefonia Microsoft

Microsoft supporta diverse opzioni durante l'avvio del viaggio in teams in Microsoft Cloud. Questo articolo consente di decidere quale soluzione di telefonia Microsoft (sistema telefonico nel cloud o VoIP aziendale locale) sia appropriata per gli utenti dell'organizzazione e in che modo l'organizzazione può connettersi alla rete PSTN (Public Switched Telephone Network). 

È consigliabile usare questo articolo insieme al diagramma tecnico associato, che fornisce un ausilio visivo per prendere la decisione giusta per l'organizzazione:

- [Soluzioni per la telefonia Microsoft-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluzioni per la telefonia Microsoft-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opzioni PBX (Private Branch Exchange)

### <a name="phone-system-office-365"></a>Sistema telefonico (Office 365)
  
Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) nel cloud di Office 365 con Microsoft teams e/o Skype for business online. 

Il sistema telefonico funziona con i team o i client Skype for business online e i dispositivi certificati. Il sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità fornite direttamente da Office 365 e strettamente integrate nell'esperienza di produttività del cloud aziendale. Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network), è possibile scegliere il piano di chiamata Microsoft o il proprio gestore di telefonia.

Per altre informazioni, vedere [cos'è il sistema telefonico in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>VoIP aziendale (Skype for Business Server)

Enterprise Voice è la tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità Private Branch Exchange (PBX) in Skype for Business Server locale. Questa opzione può essere connessa solo alla rete telefonica pubblica commutata tramite il proprio gestore di telefonia. 

Per altre informazioni, vedere [pianificare VoIP aziendale in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connessione alle opzioni PSTN (Public Switched Telephone Network)

È possibile scegliere di connettersi alla rete PSTN (Public Switched Telephone Network) tramite:

- Uso di Microsoft Calling Plan in Office 365 
- Connettere il proprio gestore di telefonia

### <a name="calling-plan-office-365"></a>Piano chiamante (Office 365)

Questa opzione connette il sistema telefonico Microsoft Office 365 alla rete PSTN (Public Switched Telephone Network) per consentire le chiamate a telefoni fissi e cellulari in tutto il mondo. Con il piano di chiamata, Microsoft è il gestore PSTN.

Per altre informazioni, vedere [chiamare piani per Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>Connettere il proprio gestore di telefonia (Office 365 e Skype for business locale)

Questa opzione connette il sistema telefonico in Office 365 o Enterprise Voice System in Skype for business locale alla rete di telefonia. Questa opzione richiede un SBC (Session Border Controller) supportato. In alcuni casi, questa opzione potrebbe richiedere il software Microsoft aggiuntivo distribuito in locale.

## <a name="which-solution-is-right-for-your-organization"></a>Quale soluzione è appropriata per l'organizzazione?

Puoi scegliere una soluzione all-in-the-cloud, una soluzione Connect-your-own-Carrier o una combinazione tra i vettori all-in-the-cloud e di terze parti:

- Sistema telefonico con piano per le chiamate (tutto nel cloud)

- Sistema telefonico con il proprio elemento portante tramite routing diretto

- Sistema telefonico con portante privato tramite Skype for Business Server o Cloud Connector Edition

- Enterprise Voice in Skype for Business Server con il proprio vettore

La soluzione scelta dipende dalle esigenze correnti e future, ad esempio:

- Se si vuole,-o è necessario,-per mantenere le funzionalità fornite dalla distribuzione locale.
- Il client che si vuole distribuire per gli utenti.
- Il piano per spostare le persone nel cloud.
- Se è necessario interagire con i PBX di terze parti e altre apparecchiature per la telefonia.

Per determinare la soluzione migliore per l'organizzazione, prendere in considerazione le domande seguenti:

- Si dispone di una distribuzione di Skype for Business Server esistente?
- Gli utenti sono ospitati in Skype for business in locale, nel cloud su Skype for business online o in entrambi? 
- Si desidera trasferire utenti locali al cloud?
- Il piano per le chiamate PSTN di Microsoft è disponibile nella tua area geografica?
- Si vuole o è necessario conservare il vettore di telefonia corrente?  Ad esempio, è necessario conservare il vettore corrente a causa di un contratto esistente?
- Si ha un PBX legacy locale esistente che si vuole o è necessario conservare?
- Il PBX legacy corrente offre caratteristiche esclusive e critiche per l'azienda?
- Qualsiasi utente o tutti gli utenti necessitano di funzionalità non attualmente disponibili nel sistema telefonico?

Tenere presente quanto segue:

- Tutte e quattro le opzioni possono coesistere tra loro in caso sia necessario progettare una soluzione per l'ambiente complesso o gestire la migrazione in più passaggi.
- Il sistema telefonico con il proprio elemento portante tramite Skype for Business Server o Cloud Connector Edition può essere distribuito solo con Skype for Business Server o Cloud Connector. La coesistenza di Skype for Business Server e Cloud Connector non è supportata in una singola società.

## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con un piano per le chiamate


Il sistema telefonico con il piano di chiamata è un'opzione all-in-the-cloud per gli utenti di teams o Skype for business online, come illustrato nel diagramma seguente:

![Sistema telefonico con un piano per le chiamate](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema telefonico Microsoft con piani di chiamate nazionali o internazionali aggiunti che consente la chiamata ai telefoni in tutto il mondo (a seconda del livello di servizio concesso in licenza). 
- Poiché il piano di chiamate PSTN funziona in Office 365, questa opzione non richiede la distribuzione o la manutenzione di una distribuzione locale.
- I clienti possono connettere un SBC supportato tramite il routing diretto per l'interoperabilità con PBX di terze parti, dispositivi analogici e altre apparecchiature di telefonia di terze parti supportate da SBC.

| Requisiti per l'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede la connessione senza interruzioni a Office 365 | Sì |
| Disponibile in tutto il mondo *                            | No  |
| Richiede la distribuzione e la gestione di un SBC (Session Border Controller) supportato | No |
| Richiede contratto con un vettore di terze parti      | No   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\*Per altre informazioni sui paesi in cui è disponibile il piano per le chiamate, vedere [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](https://docs.microsoft.com/en-us/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Se rispondi sì alle domande seguenti, questa è la soluzione giusta per te:

- Il piano di chiamata è disponibile nella tua area geografica.
- Non è necessario mantenere il gestore PSTN corrente.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN (Public Switched Telephone Network).
- Non si vogliono gestire i controller di bordo della sessione autonomamente.
- Teams e/o Skype for business online offre tutte le funzionalità richieste dall'organizzazione.

Per altre informazioni, vedere [cos'è il sistema telefonico in office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) e [piani di chiamata per Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefonico con il proprio elemento portante tramite routing diretto

Questa opzione include il sistema telefonico Microsoft nel cloud con virtualmente qualsiasi vettore di telefonia per gli utenti di teams.

![Sistema telefonico con il gestore tramite routing diretto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connettere direttamente il proprio SBC supportato a Microsoft Phone System senza bisogno di altri software locali.  
- Usare virtualmente qualsiasi gestore di telefonia con il sistema telefonico Microsoft.
- Possono essere configurati e gestiti da clienti o da un gestore o un partner (Chiedi se il gestore o il partner fornisce questa opzione).
- Configurare l'interoperabilità tra le apparecchiature di telefonia, ad esempio dispositivi PBX e analogici di terze parti, e sistema telefonico Microsoft.

| Requisiti per l'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede la connessione senza interruzioni a Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un SBC (Session Border Controller) supportato | Sì |
| Richiede contratto con il vettore di terze parti *      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | No |

\*A meno che non venga distribuito come opzione per la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature telefoniche per gli utenti che si trovano nel sistema telefonico con piani di chiamata.

Se rispondi sì alle domande seguenti, questa è la soluzione giusta per te:

- Si vuole usare teams con sistema telefonico.
- È necessario mantenere il gestore PSTN corrente.
- Si vuole mescolare il routing, alcune chiamate vengono effettuate tramite i piani di chiamata, alcuni tramite il gestore
- È necessario interagire con i PBX di terze parti e/o le attrezzature, ad esempio i pagers generali degli Stati Uniti, i dispositivi analogici
- Teams offre tutte le funzionalità necessarie per l'organizzazione.

Per altre informazioni, vedere [cos'è il sistema telefonico in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) e [pianificare il routing diretto](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefonico con portante privato tramite Skype for Business Server o Cloud Connector Edition

Questa opzione include il sistema telefonico Microsoft nel cloud con connettività a una rete di telefonia locale per gli utenti di Skype for business online.

![Sistema telefonico con il gestore tramite Skype for Business Server o Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connettere il proprio SBC supportato al sistema telefonico Microsoft tramite Skype for Business Server o Skype for Business Cloud Connector Edition distribuito in locale. 
- Usare virtualmente qualsiasi gestore di telefonia con il sistema telefonico Microsoft. 
- Se si dispone già di Skype for Business Server locale, è possibile sfruttarlo;  in caso contrario, è possibile distribuire una versione più chiara-Cloud Connector Edition.


| Requisiti per l'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede la connessione senza interruzioni a Office 365 | Sì |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un SBC (Session Border Controller) supportato | Sì |
| Richiede contratto con un vettore di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server o Cloud Connector Edition | Sì |



Se rispondi sì alle domande seguenti, questa è la soluzione giusta per te:

- Si vuole usare Skype for business online per gli utenti.
- Il piano per chiamate PSTN non è disponibile nell'area geografica.
- È necessario mantenere il gestore PSTN corrente.

Per altre informazioni, vedere [cos'è il sistema telefonico in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-server-2019)e [piano per Skype for Business Cloud Connector Edition](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Suggerimento: quando cambiano le condizioni aziendali, ad esempio non è più necessario mantenere il gestore PSTN, è consigliabile passare a Microsoft teams usando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle caratteristiche più recenti rilasciate da Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Enterprise Voice in Skype for Business Server con il proprio vettore

Questa opzione consente a Enterprise Voice locale di connettersi a una rete di telefonia locale per gli utenti locali di Skype for business.

![Enterprise Voice in Skype for Business Server con il proprio vettore](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connettere il proprio SBC supportato a Enterprise Voice System nel server locale di Skype for business.
- USA se hai bisogno di una sopravvivenza locale.
- Usare virtualmente qualsiasi gestore di telefonia con il sistema telefonico Microsoft. 
- Opzione più complessa per la distribuzione e la manutenzione.

| Requisiti per l'infrastruttura                   | Obbligatorio?|
| :----------------------------------------------------| ---------:|
| Richiede la connessione senza interruzioni a Office 365 | No |
| Disponibile in tutto il mondo                            | Sì  |
| Richiede la distribuzione e la gestione di un SBC (Session Border Controller) supportato | Sì |
| Richiede contratto con un vettore di terze parti      | Sì   |
| Richiede la distribuzione e la gestione di Skype for Business Server | Sì |

Per altre informazioni, vedere [pianificare VoIP aziendale in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Suggerimento: quando cambiano le condizioni aziendali, ad esempio non è più necessario mantenere il gestore PSTN, è consigliabile passare a Microsoft teams usando le opzioni 1 o 2 per:
- Ridurre al minimo i costi di manutenzione
- Avere accesso alle caratteristiche più recenti rilasciate da Microsoft











  
