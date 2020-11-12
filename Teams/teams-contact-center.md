---
title: Centro contatti Teams
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Panoramica della soluzione Integrated Contact Center come servizio (CCaaS) per Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee029be0d3d908820a4bf9f7cdabdb03c9e6ec83
ms.sourcegitcommit: 75eb4cce1a63cf200736790b74f4bb849e0e21ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988303"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Integrazioni di Contact Center per Microsoft Teams

L'integrazione delle più comuni soluzioni di Contact Center con Microsoft teams è una necessità comune per i clienti che implementano le funzionalità di chiamata dei team.  Questo articolo offre una panoramica del modo in cui le soluzioni Contact Center possono essere integrate con Microsoft teams e altre informazioni sulle soluzioni partner che partecipano al programma di certificazione Microsoft teams Connected Contact Center.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>Che cos'è un'integrazione di Contact Center per Microsoft Teams?

I Contact Center di oggi garantiscono molto di più del supporto: agiscono come uno dei principali veicoli per l'interazione e il feedback non filtrato sull'esperienza di un cliente con un marchio. A causa dell'ampiezza dei canali che i clienti di oggi preferiscono coinvolgere in un telefono, un messaggio di posta elettronica, un testo, un livello sociale e il volume espanso di punti di tocco associati ai processi di acquisto attuali, molte organizzazioni hanno realizzato due ulteriori realtà:

1. Ogni membro dell'organizzazione ha il potenziale per coinvolgere direttamente un cliente e quindi deve essere dotato degli strumenti appropriati.

2. Questo ambito esteso delle interazioni con i clienti richiede strumenti che consentono di gestire la coerenza, il miglioramento costante e la scalabilità.

Microsoft teams supporta i flussi di lavoro di interazione con i clienti agendo come hub per la connessione di clienti interni ed esterni attraverso le sue modalità di comunicazione, tra cui chat, riunioni video e chiamate. Per alcune aziende, le funzionalità di [cloud Voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)di Microsoft teams, incluse le code [operatore automatico](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) e [chiamate](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), garantiscono le funzionalità e la configurazione per soddisfare le proprie esigenze.

Per gli altri utenti che desiderano soluzioni integrate con strumenti aziendali e flussi di lavoro per guidare il viaggio del cliente, Microsoft teams si integra anche con alcuni dei fornitori di soluzioni di servizi di CCaaS (Leading Contact Center) del settore.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centro contatti connesso per il programma di certificazione Microsoft Teams

Le API consentono ai partner di sviluppare e integrare soluzioni CCaaS per i team. Abbiamo inoltre sviluppato il centro contatti collegato per Microsoft teams Program per garantire ai clienti la garanzia che la soluzione di ogni partner partecipante sia stata testata e verificata per garantire la qualità, la compatibilità e l'affidabilità che si aspettano da soluzioni Microsoft.

I partner seguenti sono in procinto di certificare la loro soluzione per Microsoft teams e sono pronti per coinvolgere i clienti:

|  Partner                                                                                                                               |  Sito Web della soluzione                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | www.contactcenter4all.com |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |


Questo elenco verrà aggiornato man mano che altri partner partecipano e soddisfano i criteri di certificazione.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Come funzionano le soluzioni di Contact Center in Microsoft Teams?

Microsoft teams offre una gamma di funzionalità per supportare lo sviluppo di soluzioni vocali di terze parti, tra cui:

1. [Connettività di routing diretta](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [API di comunicazione cloud di Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Piattaforma ed estensibilità Teams

4. SDK Teams

Queste funzionalità consentono insieme 3 modelli di integrazione:

  - **Connetti** (tramite routing diretto)

  - **Connettersi ed estendere** (routing diretto, API grafico e piattaforma delle app Teams)

  - **Estendere e alimentare** (incorporando SDK di teams in app 3P per le interazioni native Teams)

### <a name="connect"></a>Connettersi

Questo modello connette i partner di CCaaS con l'infrastruttura del sistema telefonico di Microsoft teams, consentendo funzionalità avanzate di routing, configurazione e sistema. In questo modello, la soluzione partner Contact Center può anche prestare servizi di telefonia per i numeri e gli utenti selezionati.

Gli agenti che usano soluzioni basate sul modello Connect possono raccogliere informazioni & approfondimenti e, se necessario, trasferire le chiamate agli esperti in materia direttamente, sfruttando la presenza delle PMI in teams per garantirne la disponibilità.

Le organizzazioni possono verificare che le chiamate instradano l'agente ottimale impostando assistenti virtuali automatizzati e code di routing basate su competenze.

**Caratteristiche principali:**

Mentre il seguente non è un elenco completo delle funzionalità di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - Office 365 AuthN per gli agenti per consentire agli agenti di connettersi al proprio tenant Microsoft dal client di CCaaS integrato 

  - Indicazione della presenza dagli utenti di Teams 

  - Flussi di chiamata tramite routing diretto (come indicato nei piani di prova) 

  - Supportare trasferimenti e raggruppare le chiamate con gli utenti di Teams 

  - API del grafico teams e API per la comunicazione cloud per l'integrazione con teams 

  - In grado di supportare il trunking SIP multi-tenant per supportare diversi clienti in SBC del partner.  

  - Partner per implementare [ <span class="underline">Microsoft Certified session border controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Connettersi ed estendere

Questo modello estende il personale dell'interfaccia di contatto e le esperienze degli agenti integrando il client teams tramite la [piattaforma client teams](https://docs.microsoft.com/microsoftteams/platform/overview), le [API teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e le API per le [comunicazioni cloud in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) e usa il sistema telefonico teams per tutte le chiamate al Contact Center e le esperienze di controllo delle chiamate. In questo modello, il partner centro contatti funge da vettore di telefonia accanto a Microsoft 365.

Sfruttando le soluzioni di connessione e estendibilità, gli agenti possono trarre vantaggio da note contestuali dinamiche che correlano i dati di più sistemi prima di avviare un impegno e quindi evitare un cambio di contesto costoso lavorando a livello nativo all'interno di team sia per la collaborazione interna che per le comunicazioni esterne.

Le organizzazioni possono progettare flussi di lavoro e configurazioni di routing avanzate fino all'individuo e misurare la qualità del sistema e delle interazioni.

**Caratteristiche principali:**

Mentre il seguente non è un elenco completo delle funzionalità di funzionalità per questo modello di integrazione, evidenzia le principali aree di interesse:

  - API del grafico teams e API per la comunicazione cloud per l'integrazione con teams 

  - App basate su team per le esperienze degli agenti 

  - Teams come endpoint delle chiamate primarie per gli agenti 

  - Client teams che chiama per tutti i controlli delle chiamate

  - L'app Agent Experience dovrebbe essere in grado di lavorare anche su Team Web e client per dispositivi mobili

  - Analisi, gestione del flusso di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in teams

  - Esperienze di chat e collaborazione integrate con i client Teams 

  - Mantenere le prestazioni e la qualità delle esperienze del client teams in tutte le app  

### <a name="extend-and-power"></a>Estendere e potere

Questo modello consente ai partner di creare applicazioni vocali native basate su Azure sfruttando i team che chiamano l'infrastruttura e la piattaforma client per offrire soluzioni moderne e intelligenti per la connessione collaborativa tra clienti e agenti. L'obiettivo di estendere e Power è quello di rifornire la creatività dello sviluppatore e guidare la produttività del cliente.

Costruendo direttamente in Azure, i partner possono implementare e provisionare rapidamente la propria soluzione in tutte le aree geografiche e geografie dei team, beneficiando della rete di comunicazioni globale condivisa, sfruttando l'archiviazione, il calcolo, l'analisi & i servizi cognitivi di Azure.

Con il modello Extend e Power Integration i partner possono offrire agli agenti del centro di contatto le esperienze di comunicazione Omni-Channel mentre incorporano l'intelligenza artificiale per personalizzare il modo in cui i partecipanti o altri servizi sono impegnati in una chiamata sfruttando l' [API per le comunicazioni cloud in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).

**Caratteristiche principali:**

Mentre il seguente non è un elenco completo delle funzionalità di funzionalità per questo modello di integrazione, queste aree evidenziate in aggiunta a quelle fornite dal modello Connetti ed Estendi.

  - Esperienze di agente formale abilitate nativamente per comunicazioni Omni-Channel tramite teams SDK 

  - Sfruttare i servizi di collaborazione di teams per le interazioni tra agenti e clienti  

  - Provisioning rapido dei servizi cloud, distribuzione ovunque 

  - Controllo diretto della conversazione e interazione con gli utenti durante le conversazioni di Teams 

### <a name="comparing-connected-contact-center-integration-models"></a>Confronto tra i modelli di integrazione di Contact Center collegati

Leggere la tabella seguente per una panoramica dei modelli di integrazione supportati da Microsoft teams.

<table>
<thead>
<tr class="header">
<th></th>
<th>App per la voce Teams</th>
<th>Connettersi</th>
<th>Estendere</th>
<th>Potere</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modello di servizio cloud</td>
<td>Azure</td>
<td>Partner</td>
<td><p>Partner +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>Chi gestisce la soluzione?</td>
<td>Microsoft</td>
<td>Partner</td>
<td>Partner</td>
<td>Partner</td>
</tr>
<tr class="odd">
<td>Accesso a M365</td>
<td>Sì</td>
<td>Sì</td>
<td>Sì</td>
<td>Sì</td>
</tr>
<tr class="even">
<td>Utenti con teams che chiamano?</td>
<td>Informale, PMI</td>
<td>Informale, PMI</td>
<td>Informale, PMI, formale</td>
<td>Informale, PMI, formale</td>
</tr>
<tr class="odd">
<td>Esperienza di IW/PMI</td>
<td>Team</td>
<td>Team</td>
<td><p>Teams +</p>
<p>estensioni</p></td>
<td><p>Teams +</p>
<p>estensioni</p></td>
</tr>
<tr class="even">
<td>Connettività del servizio</td>
<td>Piattaforma<br />
(Piani di chiamata + DR)</td>
<td>Routing diretto</td>
<td>Piattaforma<br />
(Piani di chiamata + DR)</td>
<td>Piattaforma<br />
(Piani di chiamata + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Passaggi successivi

Se si è un fornitore che cerca di partecipare al programma di certificazione, inviare un messaggio di posta elettronica <Teamscategorypartner@microsoft.com> .
