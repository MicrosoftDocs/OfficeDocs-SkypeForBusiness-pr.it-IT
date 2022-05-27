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
ms.openlocfilehash: 12e202fed6ad63835c364662194be2eabf872b31
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681927"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurare Sistema telefonico nell'organizzazione

Questo articolo fornisce una roadmap per il contenuto per la configurazione di Sistema telefonico: la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365. Alla fine di ogni passaggio sono disponibili collegamenti a informazioni più dettagliate.

Prima di leggere questo articolo, assicurati di aver letto [Cos'è Sistema telefonico](what-is-phone-system-in-office-365.md) ed [Ecco cosa ottieni con Sistema telefonico](here-s-what-you-get-with-phone-system.md). Gli ultimi due articoli descrivono Sistema telefonico requisiti e caratteristiche.

Questo articolo descrive i passaggi seguenti:

- [Passaggio 1: Acquistare e assegnare una licenza di Sistema telefonico](#step-1-buy-and-assign-a-phone-system-license)
- [Passaggio 2: Scegliere un'opzione di connettività PSTN](#step-2-choose-a-pstn-connectivity-option)
- [Passaggio 3: Ottenere i numeri di telefono per gli utenti](#step-3-get-phone-numbers-for-your-users)
- [Passaggio 4: Ottenere numeri di telefono per i servizi](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Passaggio 5: Se si vuole configurare una coda di chiamata](#step-5-if-you-want-to-set-up-a-call-queue)
- [Passaggio 6: Se vuoi configurare un operatore automatico](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Passaggio 7: Configurare i crediti comunicazioni per i numeri verdi](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Passaggio 1: Acquistare e assegnare una licenza di Sistema telefonico

Per assegnare una licenza di Sistema telefonico a un singolo utente, la procedura è la stessa dell'assegnazione di una licenza Microsoft 365.To assign a Sistema telefonico license to a single user, the steps are same as assigning a Microsoft 365 license. È anche possibile assegnare licenze a più utenti in blocco. Per altre informazioni sulle licenze di Sistema telefonico disponibili e su come acquisire e assegnare licenze, vedere [Teams licenze per componenti aggiuntivi](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) e [Assegnare licenze per Microsoft Teams componenti aggiuntivi](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Passaggio 2. Scegliere un'opzione di connettività PSTN

Per consentire agli utenti di effettuare e ricevere chiamate esterne, è necessario connettersi Sistema telefonico alla rete PSTN (Public Switched Telephone Network). Microsoft offre diverse opzioni per la connessione a PSTN, tra cui:

- Piano per chiamate. Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- Connessione con operatore. Se il gestore telefonico esistente partecipa al programma Microsoft Connessione con operatore, potrà gestire automaticamente le chiamate PSTN e i controller dei confini della sessione.

- Routing diretto. Usare il proprio gestore PSTN connettendo le SBC a Sistema telefonico.

Per altre informazioni su tutte le opzioni di connettività, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: Ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

Per informazioni su come gestire i numeri di telefono per gli utenti, vedere gli articoli seguenti. La modalità di gestione dei numeri per un utente dipende dall'opzione di connettività PSTN scelta.

- [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md) - Fornisce una panoramica dei tipi di numeri di telefono con collegamenti ad articoli specifici per l'acquisizione e la gestione dei numeri a seconda dell'opzione di connettività PSTN.
Descrive i due tipi di [numeri di telefono utente](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Assegnare, modificare o rimuovere un numero di telefono per un utente](assign-change-or-remove-a-phone-number-for-a-user.md) : descrive come assegnare e gestire i numeri di telefono acquisiti.

- [Quanti numeri di telefono è possibile ottenere](how-many-phone-numbers-can-you-get.md) – Descrive il numero di numeri di telefono che è possibile ottenere in base ai tipi di numeri di telefono e ai tipi di licenza acquistati e assegnati.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Passaggio 4: Ottenere numeri di telefono per i servizi (code di chiamata, operatori automatici)

Oltre a ottenere numeri di telefono per gli utenti, puoi acquisire numeri a pagamento o numeri verdi per servizi come gli operatori automatici e le code di chiamata. Un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente.

È possibile ottenere da Microsoft numeri di servizio inclusi nelle licenze. Se la connettività PSTN è disponibile tramite Connessione con operatore o Direct Routing, è possibile utilizzare i numeri di servizio forniti dal gestore o dall'operatore di telefonia mobile.

Per ulteriori informazioni, vedere:

- [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md) - Fornisce una panoramica dei tipi di numeri di telefono con collegamenti ad articoli specifici per l'acquisizione e la gestione dei numeri a seconda dell'opzione di connettività PSTN.
Descrive i [numeri di telefono di servizio](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponibili da Microsoft inclusi nelle licenze. Per informazioni sui numeri di servizio forniti da Connessione con operatore o Direct Routing, contattare il provider.

- [Quanti numeri di telefono è possibile ottenere](how-many-phone-numbers-can-you-get.md) – Descrive il numero di numeri di telefono che è possibile ottenere in base ai tipi di numeri di telefono e ai tipi di licenza acquistati e assegnati.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Passaggio 5: Se si vuole configurare una coda di chiamata

Le code di chiamata includono i saluti utilizzati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata. È possibile creare una o più code di chiamata per l'organizzazione.

Per altre informazioni sulle code di chiamata, vedere [Creare una coda di chiamata](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Passaggio 6: Se vuoi configurare un operatore automatico

Gli operatori automatici consentono alle persone che chiamano la tua organizzazione di navigare in un sistema di menu per portarli al reparto, alla coda di chiamata, alla persona o all'operatore giusto.

Per informazioni sulla configurazione degli operatori automatici, vedi [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Passaggio 7: Configurare i Crediti comunicazioni per i numeri verdi

Se desideri utilizzare i numeri verdi con Microsoft Teams, dovrai configurare i Crediti comunicazioni. Le chiamate a numero verde sono fatturate a minuti e richiedono un saldo positivo di Crediti comunicazioni.

I Crediti comunicazioni sono un modo comodo per aggiungere numeri verdi da utilizzare come indicato di seguito:

- Con i numeri di servizio per le app vocali, ad esempio gli operatori automatici o le code di chiamata.

- Per comporre qualsiasi numero di telefono internazionale quando hai un abbonamento al Piano per chiamate nazionali o superiore a quello incluso in un abbonamento a un piano per chiamate nazionali e internazionali.

- Per effettuare chiamate in uscita e pagare al minuto una volta esaurito l'assegnazione di minuti mensili.

Per ulteriori informazioni, vedi [Che cosa sono i Crediti comunicazioni?](what-are-communications-credits.md) e [Impostare i Crediti comunicazioni per la tua organizzazione](set-up-communications-credits-for-your-organization.md).

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Sistema telefonico](what-is-phone-system-in-office-365.md)

- [Vantaggi offerti da Sistema telefonico](here-s-what-you-get-with-phone-system.md)

- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-landing-page.md)
