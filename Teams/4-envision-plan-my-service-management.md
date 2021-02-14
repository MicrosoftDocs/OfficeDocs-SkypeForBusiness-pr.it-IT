---
title: Pianificare la gestione dei servizi di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Distribuire e mantenere una distribuzione di alta qualità pianificando i ruoli operativi e assegnando un campione della qualità.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74d07cc40adf8010c2d987e05669264f8cc1367
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610031"
---
# <a name="plan-my-service-management"></a>Pianificare la gestione dei servizi

Questo articolo offre una panoramica dei requisiti necessari per distribuire e mantenere una distribuzione di Microsoft Teams di alta qualità. È possibile assicurare una distribuzione corretta pianificando la gestione e la qualità dei servizi durante la fase di sviluppo, prima della prima distribuzione pilota o di produzione.

## <a name="service-management-for-teams"></a>Gestione dei servizi per Teams

La gestione del servizio è un argomento generale che illustra le operazioni quotidiane del servizio Microsoft Teams dopo la distribuzione e l'a attivazione per gli utenti. Il servizio Teams comprende Microsoft 365 o Office 365 e i componenti dell'infrastruttura distribuiti in locale (ad esempio la rete).

Molto probabilmente non si tratta di un nuovo concetto per la maggior parte delle organizzazioni. È probabile che siano già stati implementati processi e attività associati a servizi esistenti. Detto questo, è probabile che si possa incrementare ciò che è in essere quando si pianifica oggi la gestione dei servizi per supportare Microsoft Teams in futuro.

La gestione del servizio comprende tutte le attività e i processi coinvolti nella gestione end-to-end di Microsoft Teams. Alcuni componenti della gestione dei servizi, ovvero i componenti dell'infrastruttura costituiti dal servizio Microsoft 365 o Office 365 stesso, sono responsabilità di Microsoft, mentre il cliente è responsabile per gli utenti di gestire i vari aspetti di Teams, la rete e gli endpoint che forniscono.
Per una discussione completa sulla responsabilità del cliente per la gestione dei servizi di Teams e su come si relaziona con i principali componenti alla base della qualità dell'esperienza utente, vedere Pianificare la gestione e la qualità dei [servizi.](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

![Diagramma dei tre componenti della qualità](media/plan-my-service-management-image1.png "Diagramma dei tre componenti della qualità, servizio, rete ed endpoint di Microsoft 365 o Office 365, e il modo in cui la gestione dei servizi si sovrappone a tutte e tre.")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>Introduzione alla Guida alle operazioni 

**Quali** **sono, Chi** e **In che modo** sono tre le domande importanti a cui occorre rispondere per quanto riguarda la gestione dei servizi.

È possibile usare la [Guida alle operazioni](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) per rispondere a tutte e tre queste domande. La guida fornisce un elenco delle attività da eseguire su base giornaliera, settimanale, mensile e in base alle esigenze. Queste attività e attività sono essenziali per mantenere una distribuzione di Teams di alta qualità. Stabilire chi sarà responsabile dell'esecuzione di attività specifiche nella gestione dei servizi è un aspetto fondamentale della pianificazione che è necessario eseguire all'inizio della fase di definizione per assicurare la riuscita della distribuzione. Dopo aver compreso le attività e le attività, è necessario comprenderle e seguirle con i gruppi o gli utenti assegnati. La Guida alle operazioni fornisce informazioni e indicazioni su come eseguire ognuna delle attività e/o riferimenti a contenuto esterno.

## <a name="plan-for-operational-role-mapping"></a>Pianificare il mapping del ruolo operativo

La pianificazione iniziale della gestione dei servizi è un'attività cardine fondamentale, perché la fase delle operazioni inizia quando vengono abilitati i primi utenti del progetto pilota. Il team di progetto deve rivedere e concordare le attività e le attività richieste, identificare il team responsabile di ogni attività operativa, quindi ottenere un impegno e una firma da ogni team.

Una volta completata l'autorizzazione, il team responsabile deve iniziare a operare su questi ruoli e responsabilità. Può includere formazione e preparazione, aggiornare il modello di gestione del personale o verificare che i partner esterni siano pronti per la distribuzione.

La mappatura dei ruoli operativi all'inizio della fase divisione consente a tutti i team di avviare le attività operative durante il progetto pilota e di configurare le operazioni e verificare che tutto sia pronto dopo l'inizio della distribuzione.

La Guida alle operazioni fornisce un elenco delle attività comuni mappate a ruoli tipici che devono essere validi nella maggior parte degli scenari. È necessario personalizzare queste responsabilità per l'organizzazione.

>[!TIP]
>Di seguito è riportato un esempio di modello per documentare il risultato dell'esercizio di mapping dei ruoli operativi eseguito per supportare il progetto.


|Ruolo operativo |Descrizione |Team |Dettagli contatto |
|---------|---------|---------|---------|
|Proprietario del servizio|Proprietario del servizio, interfaccia per divisioni aziendali, strategia|TBA|TBA|
|Operazioni di audioconferenza|Operazioni quotidiane, spostamento/aggiunta/modifica dell'account utente e dispositivo, monitoraggio|TBA| TBA| 
|Amministratore tenant|Modificare le impostazioni a livello di tenant e abilitare le nuove caratteristiche|TBA|TBA|
|Help Desk|Interfaccia che consente agli utenti di ottenere supporto|TBA|TBA|
|Operazioni di rete|Eseguire l'accesso a LAN, WAN, Wi-Fi e Internet|TBA|TBA|
|Team degli & client|Gestire le distribuzioni desktop|TBA|TBA|
|Operazioni di identità|Gestire l'infrastruttura di gestione delle identità (Active Directory, Active Directory Federation Services, Azure AD)|TBA|TBA|
|Adozione/gestione delle modifiche|Gestire consapevolezza, formazione e adozione per la soluzione|TBA|TBA|
|Operazioni di Exchange|Gestire l'ambiente di Exchange|TBA|TBA|
|Operazioni telefoniche|Gestire l'SBC e i numeri di telefono|TBA|TBA|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>Ruolo di campione della qualità

Un gruppo o una persona deve essere contabile per la qualità in tutte le organizzazioni.
Questo è il ruolo più importante nella gestione dei servizi. Il campione della qualità è un ruolo del cliente assegnato a una persona o a un gruppo che si è appassionati dell'esperienza degli utenti. Questo ruolo richiede le competenze necessarie per identificare le tendenze nell'ambiente e la sponsorizzazione di collaborare con altri team per guidare la correzione.
Il candidato migliore per il campione della qualità è in genere il proprietario del servizio clienti, che, a seconda delle dimensioni e della complessità dell'organizzazione, potrebbe essere qualsiasi persona o gruppo che abbia una grande familiarità con l'esperienza utente.

Il campione della qualità sfrutta gli strumenti e i processi documentati esistenti, come Call Quality Dashboard (CQD) e la Guida alla revisione dell'esperienza della qualità, per monitorare l'esperienza utente, identificare le tendenze della qualità e guidare la correzione, se necessario. Il campione della qualità collabora con i rispettivi team per guidare le azioni di correzione, segnalando a un comitato competente sui loro progressi e i problemi aperti.

Le attività e le attività associate al ruolo sono documentate nella Guida al funzionamento. Questo ruolo dovrebbe essere assegnato nella prima fase di Envision. Un passaggio fondamentale per l'operatività del ruolo di Campione della qualità consiste nell'acquisire le conoscenze necessarie per il ruolo e assicurarsi che siano soddisfatti i prerequisiti per l'esecuzione delle attività. Un'attività chiave per questo ruolo è eseguire una normale verifica dell'esperienza qualità.

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>Introduzione alla guida di revisione dell'esperienza di qualità

La guida al controllo qualità include un set di attività che valutano e forniscono indicazioni per la correzione nelle aree chiave che hanno il maggior impatto sul miglioramento dell'esperienza utente, come illustrato nella figura seguente.

![Illustrazione delle aree principali da esaminare durante la revisione dell'esperienza di qualità](media/plan-my-service-management-image2.png "Aree chiave da esaminare durante una verifica della qualità: audio, affidabilità e risultati dei sondaggi degli utenti.")

Valutando e correndo continuamente le aree descritte in questo documento, è possibile ridurre il rischio di influire negativamente sull'esperienza utente. La maggior parte dei problemi di esperienza utente che si verificano in una distribuzione può essere raggruppata nelle categorie seguenti:

-   Configurazione incompleta del firewall o del proxy

-   Copertura Wi-Fi scarsa

-   Larghezza di banda insufficiente

-   VPN

-   Uso di dispositivi audio non supportati o incorporati

-   Subnet o dispositivi di rete problematici

Le indicazioni fornite nella Guida alla revisione dell'esperienza di qualità si focalizzano sull'uso di Call Quality Dashboard (CQD) Online come strumento principale per la segnalazione e l'analisi di ogni area descritta, concentrando l'attenzione sull'audio per ottimizzare l'adozione e l'impatto. Le ottimizzazioni apportate alla rete per migliorare l'esperienza audio verranno anche tradotte direttamente in miglioramenti nella condivisione di video e desktop.

Consigliamo vivamente di nominare il campione della qualità fin dall'inizio. Dopo essere stati nominati, dovrebbero iniziare ad acquisire familiarità con il contenuto della guida alla revisione [dell'esperienza di qualità.](https://aka.ms/qerguide)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidi chi è l'amministratore per le operazioni vocali cloud nell'organizzazione.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Scaricare la guida completa pianificazione per la gestione dei servizi.</li><li>Scarica la guida alla verifica dell'esperienza di qualità.</li><li>Esaminare completamente la Guida alle operazioni.</li><li>Fornire tutte le guide a tutti i membri del team per le operazioni per esaminare e conoscere i requisiti per le operazioni.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
