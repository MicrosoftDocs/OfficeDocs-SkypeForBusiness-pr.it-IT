---
title: Espansione delle impostazioni generali di Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni per un Survivable Branch Appliance o un Survivable Branch Server esistente, vengono presentate le sezioni seguenti:'
ms.openlocfilehash: 97f12828a8513ce284f4cd14c06de3496100c313
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702391"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Espansione delle impostazioni generali di Survivable Branch Appliance

Per modificare le impostazioni per un Survivable Branch Appliance o un Survivable Branch Server esistente, vengono presentate le sezioni seguenti:

- Impostazioni generali

- Impostazioni di resilienza

- Impostazioni del Mediation Server


Per un Survivable Branch Appliance o Survivable Branch Server, viene presentato il codice seguente:

### <a name="general-settings"></a>Impostazioni generali

Il nome di dominio completo (FQDN) di Survivable Branch Appliance o Survivable Branch Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.

È possibile selezionare **Usa tutti gli indirizzi IP configurati** o **Limita utilizzo servizio a indirizzi IP selezionati**. Se si seleziona **Limita utilizzo servizio a indirizzi IP selezionati**, sarà necessario definire l'indirizzo IP primario che verrà usato dal server per tutte le comunicazioni, tranne per il gateway PSTN (Public Switched Telephone Network). Sarà necessario definire un indirizzo IP separato per l'utilizzo PSTN.

In **Associazioni** è possibile modificare o specificare quanto segue:

- Associa server di archiviazione consente di selezionare per associare un server di archiviazione a Survivable Branch Appliance o Survivable Branch Server. È possibile selezionare un server di archiviazione già definito selezionando il server nell'elenco a discesa oppure fare clic su **nuovo** per specificare un nuovo server di archiviazione.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

- Il server di monitoraggio associato consente di selezionare per associare un server di monitoraggio a Survivable Branch Appliance o Survivable Branch Server. È possibile selezionare un server di monitoraggio già definito selezionando il server nell'elenco a discesa oppure fare clic su **nuovo** per specificare un nuovo server di monitoraggio.

- Associa Edge pool consente di selezionare per associare un server perimetrale o un pool con Survivable Branch Appliance o Survivable Branch Server. È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco a discesa oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.

### <a name="resiliency"></a>Resilienza

La resilienza garantisce una disponibilità elevata per il pool di registrazione. Fornendo una funzione di registrazione di backup, in caso di malfunzionamento della funzione di registrazione principale, quella di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi con la funzione di registrazione principale.

Nell'elenco a discesa selezionare il pool di front end Enterprise Edition o il server front end Standard Edition che fungerà da registrar per il Survivable Branch Appliance o Survivable Branch Server. È inoltre possibile scegliere di impostare intervalli di tempo per il failover e il fallback. Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di una funzione di registrazione con problemi ed è previsto un periodo di tempo per determinare automaticamente se la funzione di registrazione principale sia di nuovo attiva e pronta per riacquisire il controllo del processo di registrazione.

> [!IMPORTANT]
> Nel definire l'intervallo di rilevamento degli errori e l'intervallo di fallback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al fallback se la funzione di registrazione non risponde per un breve periodo di tempo. È infatti possibile che la funzione di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server. I valori predefiniti per un Survivable Branch Appliance o un Survivable Branch Server in un sito a un pool o a un server front-end Standard Edition sono 120 secondi per il failover e 240 secondi per il fallback.

### <a name="mediation-server"></a>Mediation Server

Per il **Mediation Server** è possibile specificare quanto segue:

La casella di controllo per **Mediation Server collocata abilitata** non è disponibile in un Survivable Branch Appliance o Survivable Branch Server perché il Mediation Server è collocato.

Definire la porta di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.

Puoi definire i gateway PSTN associati al Mediation Server collocato. Se sono già stati definiti gateway, saranno disponibili per l'associazione con il Mediation Server. Se i gateway non sono stati definiti ma sono disponibili per la definizione, sarà possibile selezionare **Nuovo**. È anche possibile rimuovere i gateway già configurati per il Mediation Server. A tale scopo, selezionare il gateway e quindi fare clic su **Rimuovi**.

Se si ha più di un gateway associato a un Mediation Server, il primo gateway associato sarà il gateway predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**.


Per informazioni dettagliate su come definire e configurare le impostazioni per Survivable Branch Appliance o Survivable Branch Server, vedere [soluzioni di resilienza dei siti di succursale](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


