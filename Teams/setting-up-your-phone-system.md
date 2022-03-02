---
title: Configurare Sistema telefonico nell'organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Guida dettagliata che illustra come configurare Teams Sistema telefonico per l'organizzazione in Microsoft 365.
ms.openlocfilehash: 3a5c275c7d7d881ff770e6e84a3d4fa935d2827f
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043344"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurare Sistema telefonico nell'organizzazione

Questo articolo fornisce una roadmap per il contenuto per la configurazione di Sistema telefonico, ovvero la tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365. Alla fine di ogni passaggio sono disponibili collegamenti a informazioni più dettagliate. 

Prima di leggere questo articolo, assicurarsi di aver letto Cosa [](what-is-phone-system-in-office-365.md) c'è Sistema telefonico e Ecco cosa si ottiene con [Sistema telefonico](here-s-what-you-get-with-phone-system.md). Gli ultimi due articoli descrivono Sistema telefonico e le funzionalità.    

Questo articolo descrive i passaggi seguenti: 

- [Passaggio 1: Acquistare e assegnare una Sistema telefonico licenza](#step-1-buy-and-assign-a-phone-system-license)  
- [Passaggio 2: Scegliere un'opzione di connettività PSTN](#step-2-choose-a-pstn-connectivity-option) 
- [Passaggio 3: Ottenere i numeri di telefono per gli utenti](#step-3-get-phone-numbers-for-your-users)
- [Passaggio 4: Ottenere i numeri di telefono per i servizi](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Passaggio 5: Se si vuole configurare una coda di chiamata](#step-5-if-you-want-to-set-up-a-call-queue) 
- [Passaggio 6: Se si vuole configurare un operatore automatico](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [Passaggio 7: Configurare i crediti di comunicazione per i numeri verde](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Passaggio 1: Acquistare e assegnare una Sistema telefonico licenza

Per assegnare una Sistema telefonico a un singolo utente, i passaggi sono gli stessi dell'assegnazione di una Microsoft 365 licenza. È anche possibile assegnare licenze a più utenti in blocco. Per altre informazioni sulle licenze Sistema telefonico disponibili e su come acquisire e assegnare licenze, vedere  [Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) Licenze per componenti aggiuntivi e Assegnare licenze per Teams di [componenti aggiuntivi Microsot](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Passaggio 2. Scegliere un'opzione di connettività PSTN 
 
Per consentire agli utenti di effettuare e ricevere chiamate esterne, è necessario connettersi Sistema telefonico rete PSTN (Public Switched Telephone Network). Microsoft offre più opzioni per la connessione alla rete PSTN, tra cui: 

- Piano chiamate. Una soluzione all-in-the-cloud con Microsoft come gestore PSTN. 

- Connessione con operatore. Se il gestore esistente partecipa al programma Microsoft Connessione con operatore, può gestire le chiamate PSTN e i session border controller (SBC) per l'utente. 

- Instradamento diretto. Usa il tuo gestore PSTN collegando i tuoi SBC a Sistema telefonico. 

Per altre informazioni su tutte le opzioni di connettività, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).   

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: Ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

Per informazioni su come gestire i numeri di telefono per gli utenti, vedere gli articoli seguenti. La modalità di gestione dei numeri per un utente dipende dall'opzione di connettività PSTN scelta.   

- [Gestire i numeri di telefono per](manage-phone-numbers-landing-page.md) l'organizzazione: offre una panoramica dei tipi di numeri di telefono con collegamenti ad articoli specifici per l'acquisizione e la gestione dei numeri a seconda dell'opzione di connettività PSTN. Descrive i due tipi di [numeri di telefono degli utenti](manage-phone-numbers-landing-page.md#user-telephone-numbers). 
 
- [Assegnare, modificare o rimuovere un](assign-change-or-remove-a-phone-number-for-a-user.md) numero di telefono per un utente: descrive come assegnare e gestire i numeri di telefono acquistati. 
 
- [Quanti numeri di](how-many-phone-numbers-can-you-get.md) telefono è possibile ottenere: descrive quanti numeri di telefono è possibile ottenere a seconda dei tipi di numeri di telefono e dei tipi di licenze acquistati e assegnati. 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Passaggio 4: Ottenere i numeri di telefono per i servizi (code di chiamata, operatori automatici)

Oltre a ricevere i numeri di telefono per gli utenti, è possibile acquistare numeri a numero verde o a numero verde per servizi come operatori automatici e code di chiamata. Un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente.   

È possibile ottenere da Microsoft i numeri di servizio inclusi nelle licenze. Se si dispone di connettività PSTN tramite Connessione con operatore o Routing diretto, è possibile usare i numeri di servizio forniti dal proprio gestore o operatore. 

Per ulteriori informazioni, vedere:

- [Gestire i numeri di telefono per](manage-phone-numbers-landing-page.md) l'organizzazione: offre una panoramica dei tipi di numeri di telefono con collegamenti ad articoli specifici per l'acquisizione e la gestione dei numeri a seconda dell'opzione di connettività PSTN.  
Descrive i [numeri di telefono del](manage-phone-numbers-landing-page.md#service-telephone-numbers) servizio disponibili da Microsoft inclusi nelle licenze. Per informazioni sui numeri di servizio forniti da Connessione con operatore o Routing diretto, contattare il provider. 

- [Quanti numeri di](how-many-phone-numbers-can-you-get.md) telefono è possibile ottenere: descrive quanti numeri di telefono è possibile ottenere a seconda dei tipi di numeri di telefono e dei tipi di licenze acquistati e assegnati. 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Passaggio 5: Se si vuole configurare una coda di chiamata

Le code di chiamata includono i messaggi di saluto usati quando qualcuno chiama a un numero di telefono dell'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata. È possibile creare una o più code di chiamata per l'organizzazione. 

Per altre informazioni sulle code di chiamata, vedere [Creare una coda di chiamata](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Passaggio 6: Se si vuole configurare un operatore automatico

Gli operatori automatici consentono alle persone che chiamano l'organizzazione di spostarsi in un sistema di menu per accedervi al reparto, alla coda di chiamata, alla persona o all'operatore giusto.  

Per informazioni sulla configurazione degli operatori automatici, vedere  [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Passaggio 7: Configurare i crediti comunicazioni per i numeri verde

Se si desidera utilizzare numeri verde con Microsoft Teams, è necessario configurare Crediti comunicazioni. Le chiamate a numero verde sono fatturate a minuti e richiedono un saldo positivo di Crediti comunicazioni. 

I Crediti comunicazioni sono un modo pratico per aggiungere numeri verde da usare come segue: 

- Con i numeri di servizio per le app vocali, ad esempio gli operatori automatici o le code di chiamata. 

- Per comporre un numero di telefono internazionale quando si hanno abbonamenti al Piano per chiamate nazionali o oltre a quello incluso in un abbonamento al Piano per chiamate nazionali e internazionali. 

- Per effettuare chiamate in uscita e pagare al minuto dopo aver esaurito l'assegnazione mensile dei minuti. 

Per altre informazioni,  [vedereChe cos'sono i crediti comunicazioni?](what-are-communications-credits.md) e [Configurare i crediti comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Sistema telefonico](what-is-phone-system-in-office-365.md)

- [Vantaggi offerti da Sistema telefonico](here-s-what-you-get-with-phone-system.md)

- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-landing-page.md)


    
  
 
