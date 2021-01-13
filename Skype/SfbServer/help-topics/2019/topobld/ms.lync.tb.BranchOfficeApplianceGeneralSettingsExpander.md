---
title: Espansione delle impostazioni generali di Survivable Office Appliance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un Survivable Branch Appliance o Survivable Branch Server esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: a191c89fc41bc5a4fc7f33c2e6802c87455259f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811276"
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

- Il server di archiviazione associato consente di scegliere di associare un server di archiviazione a Survivable Branch Appliance o Survivable Branch Server. È possibile selezionare un server di archiviazione già definito selezionando il server nell'elenco a discesa oppure fare clic su **nuovo** per specificare un nuovo server di archiviazione.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

- Il server di monitoraggio associato consente di scegliere di associare un server di monitoraggio a Survivable Branch Appliance o Survivable Branch Server. È possibile selezionare un server di monitoraggio già definito selezionando il server dall'elenco a discesa oppure fare clic su **nuovo** per specificare un nuovo server di monitoraggio.

- Associa pool di server perimetrali consente di selezionare l'associazione di un pool o di uno spigolo con Survivable Branch Appliance o Survivable Branch Server. È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco a discesa oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.

### <a name="resiliency"></a>Con resilienza

La resilienza garantisce una disponibilità elevata per il pool di registrazione. Fornendo una funzione di registrazione di backup, in caso di malfunzionamento della funzione di registrazione principale, quella di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi con la funzione di registrazione principale.

Nell'elenco a discesa selezionare il pool Enterprise Edition front end o il server Standard Edition front end che fungerà da registrazione di backup per Survivable Branch Appliance o Survivable Branch Server. È inoltre possibile scegliere di impostare intervalli di tempo per il failover e il failback. Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di una funzione di registrazione con problemi ed è previsto un periodo di tempo per determinare automaticamente se la funzione di registrazione principale sia di nuovo attiva e pronta per riacquisire il controllo del processo di registrazione.

> [!IMPORTANT]
> Nel definire l'intervallo di rilevamento degli errori e l'intervallo di failback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al failback se la funzione di registrazione non risponde per un breve periodo di tempo. È infatti possibile che la funzione di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server. I valori predefiniti per un Survivable Branch Appliance o un Survivable Branch Server in un sito per un pool o un server Standard Edition front end sono 120 secondi per il failover e 240 secondi per il fallback.

### <a name="mediation-server"></a>Mediation Server

Per **Mediation Server** è possibile specificare quanto segue:

La casella di controllo **Mediation Server nella stessa posizione abilitato** non è disponibile per un Survivable Branch Appliance o un Survivable Branch Server perché il Mediation Server è collocato.

Definire la porta di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.

Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server. Se i gateway non sono stati definiti ma sono disponibili per la definizione, sarà possibile selezionare **Nuovo**. Sarà inoltre possibile rimuovere i gateway già configurati per il Mediation Server. A tale scopo, selezionare il gateway e quindi fare clic su **Rimuovi**.

Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**.


Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il Survivable Branch Appliance o il Survivable Branch Server, vedere [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


