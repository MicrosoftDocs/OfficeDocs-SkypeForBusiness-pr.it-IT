---
title: Espansione delle impostazioni generali di Survivable Office Appliance
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un Survivable Branch Appliance o Survivable Branch Server esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: 687b5ea791b246d0bef2d460376c809f9272417a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775406"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Espansione delle impostazioni generali di Branch Office Appliance

Per modificare le impostazioni di un Survivable Branch Appliance o Survivable Branch Server esistente, sono disponibili le sezioni seguenti:

- Impostazioni generali

- Impostazioni di resilienza

- Impostazioni del Mediation Server


Per un Survivable Branch Appliance o un Survivable Branch Server, sono disponibili le impostazioni seguenti:

### <a name="general-settings"></a>Impostazioni generali

Nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.

È possibile selezionare **Usa tutti gli indirizzi IP configurati** o **Limita utilizzo servizio a indirizzi IP selezionati**. Se si seleziona **Limita utilizzo servizio a indirizzi IP selezionati**, sarà necessario definire l'indirizzo IP primario che verrà usato dal server per tutte le comunicazioni, tranne per il gateway PSTN (Public Switched Telephone Network). Sarà necessario definire un indirizzo IP separato per l'utilizzo PSTN.

In **Associazioni** è possibile modificare o specificare quanto segue:

- Associa server di archiviazione consente di scegliere di associare un server di archiviazione al Survivable Branch Appliance o al Survivable Branch Server. È possibile eseguire una selezione da un server di archiviazione già definito selezionandolo nell'elenco a discesa oppure fare clic su **Nuovo** per specificare un nuovo server di archiviazione.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

- Associa Monitoring Server consente di scegliere di associare un Monitoring Server al Survivable Branch Appliance o al Survivable Branch Server. È possibile eseguire una selezione da un Monitoring Server già definito selezionando il server nell'elenco a discesa oppure fare clic su **Nuovo** per specificare un nuovo Monitoring Server.

- Associa pool di server perimetrali consente di scegliere di associare un server perimetrale o un pool al Survivable Branch Appliance o al Survivable Branch Server. È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco a discesa oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.

### <a name="resiliency"></a>Resilienza

La resilienza garantisce una disponibilità elevata per il pool di registrazione. Fornendo una funzione di registrazione di backup, in caso di malfunzionamento della funzione di registrazione principale, quella di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi con la funzione di registrazione principale.

Nell'elenco a discesa selezionare il pool edizione Enterprise Front End o edizione Standard Front End Server che fungerà da registrar di backup per il Survivable Branch Appliance o il Survivable Branch Server. È inoltre possibile scegliere di impostare intervalli di tempo per il failover e il failback. Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di una funzione di registrazione con problemi ed è previsto un periodo di tempo per determinare automaticamente se la funzione di registrazione principale sia di nuovo attiva e pronta per riacquisire il controllo del processo di registrazione.

> [!IMPORTANT]
> Nel definire l'intervallo di rilevamento degli errori e l'intervallo di failback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al failback se la funzione di registrazione non risponde per un breve periodo di tempo. È infatti possibile che la funzione di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server. I valori predefiniti per un Survivable Branch Appliance o un Survivable Branch Server in un sito in un pool o edizione Standard Front End Server sono 120 secondi per il failover e 240 secondi per il fallback.

### <a name="mediation-server"></a>Mediation Server

Per **Mediation Server** è possibile specificare quanto segue:

La casella di controllo **Mediation Server nella stessa posizione abilitato** non è disponibile per un Survivable Branch Appliance o un Survivable Branch Server perché il Mediation Server è collocato.

Definire la porta di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.

Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server. Se i gateway non sono stati definiti ma sono disponibili per la definizione, sarà possibile selezionare **Nuovo**. Sarà inoltre possibile rimuovere i gateway già configurati per il Mediation Server. A tale scopo, selezionare il gateway e quindi fare clic su **Rimuovi**.

Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**.


Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il Survivable Branch Appliance o il Survivable Branch Server, vedere [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).