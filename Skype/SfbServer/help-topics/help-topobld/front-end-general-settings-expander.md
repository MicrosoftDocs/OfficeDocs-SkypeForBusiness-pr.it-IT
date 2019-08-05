---
title: Espansione delle impostazioni generali di Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Per modificare le impostazioni per un pool Front End o un server Standard Edition esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: bd4cbb507bff025f7133673c25f59beada37aeb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189914"
---
# <a name="front-end-general-settings-expander"></a>Espansione delle impostazioni generali di Front End Server

Per modificare le impostazioni per un pool Front End o un server Standard Edition esistente, sono disponibili le sezioni seguenti:

- Impostazioni generali

- Impostazioni di resilienza

- Impostazioni dei servizi Web

- Impostazioni del Mediation Server

## <a name="front-end-pool"></a>Pool Front End

Per un pool Front End, è possibile configurare impostazioni generali, di resilienza, dei servizi Web e del Mediation Server. Per informazioni dettagliate, vedere le sottosezioni riportate di seguito. Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il pool Front End, vedere [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Impostazioni generali

È possibile configurare le impostazioni generali seguenti:

- **FQDN**. Modificare l'FQDN del pool per cambiarlo.

- **Abilita la porta di monitoraggio del bilanciamento del carico hardware**. Selezionare la casella di controllo e immettere il numero di porta che il dispositivo di bilanciamento del carico hardware userà per monitorare lo stato dei server del pool.

- In **Caratteristiche e funzionalità** definire gli ulteriori ruoli che si desidera collocare nel pool. È possibile configurare le impostazioni seguenti:

  - **Servizio di conferenza**. Include audio, video e condivisione applicazioni. Dopo avere selezionato questa opzione, è possibile selezionare Servizi di conferenza telefonica con accesso esterno (PSTN). È possibile specificare e definire un gateway PSTN (Public Switched Telephone Network) più avanti nella sottosezione "Impostazioni del Mediation Server" di questa sezione.

  - **VoIP aziendale**. Consente le chiamate vocali interne tramite IP a telefoni e dispositivi qualificati e ai client Skype for business. Per abilitare le funzionalità di chiamata esterna, è necessario includere un Mediation Server. Per informazioni dettagliate, vedere "Mediation Server" più avanti in questo argomento.

- In **Associazioni** modificare o specificare quanto segue:

  - **Archivio SQL**. Modificare un database SQL Server esistente o creare un nuovo database basato su SQL Server in cui inserire i database del pool Front End. È possibile selezionare una nuova istanza di SQL Server nell'elenco oppure creare una nuova voce facendo clic su **Nuovo**.

    Selezionare **Abilita mirroring dell'archivio SQL Server** e quindi il server da usare per il mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

    Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** per selezionare un server da usare come controllo del mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

  - **Condivisione file**. Modificare l'archivio file usato dal pool Front End. È possibile usare un nuovo archivio file tra quelli già definiti selezionandolo nell'elenco oppure creare un nuovo archivio file facendo clic su **Nuovo**.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

  - **Archiviazione**. Associare un archivio del server di archiviazione al pool Front End. È possibile usare un archivio SQL Server per l'archiviazione già definito selezionandolo nell'elenco oppure specificare un nuovo server di archiviazione facendo clic su **Nuovo**.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

    Selezionare **Abilita mirroring dell'archivio SQL Server** e quindi il server da usare per il mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

    Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** per selezionare un server da usare come controllo del mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

  - **Monitoraggio (CDR e metrica QoE)**. Selezionare questa opzione per associare un archivio SQL Server per il monitoraggio al pool Front End. È possibile usare un Monitoring Server già definito selezionandolo nell'elenco oppure specificare un nuovo Monitoring Server facendo clic su **Nuovo**.

    Selezionare **Abilita mirroring dell'archivio SQL Server** e quindi il server da usare per il mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

    Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** per selezionare un server da usare come controllo del mirroring. Fare clic su **Nuovo** per creare un nuovo archivio SQL Server.

  - **Associa pool di server perimetrali (per componenti multimediali)**. Associare un server perimetrale o un pool di server perimetrali al pool Front End. È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.

  - **Associa il pool a un server Office Web Apps**. Selezionare questa opzione per associare un server Office Web Apps a un pool Front End. È possibile selezionare un server esistente nell'elenco oppure crearne uno nuovo facendo clic su **Nuovo**.

### <a name="resiliency"></a>Resilienza

La resilienza fornisce al pool funzionalità di ripristino di emergenza e disponibilità elevata. Fornendo un server di backup, in caso di malfunzionamento del server principale, quello di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi con il server principale.

Selezionare nell'elenco il pool Front End o il server Standard Edition che opererà come server di backup per il pool. È inoltre possibile impostare intervalli di tempo per il failover e il fallback. Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di un server con problemi ed è previsto un periodo di tempo per determinare automaticamente se il server principale sia di nuovo attivo.

> [!IMPORTANT]
> Nel definire l'intervallo di rilevamento degli errori e l'intervallo di fallback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al fallback se il server non risponde per un breve periodo di tempo. È infatti possibile che il server principale non risponda per brevi periodi a causa del caricamento del pool o dei server. I valori predefiniti per il failover e il fallback sono di 300 secondi e 600 secondi da un pool all'altro oppure da un pool a un server Standard Edition. Nel caso di un Survivable Branch Appliance o di un Survivable Branch Server da un sito a un pool oppure a un server Standard Edition, i valori predefiniti sono di 120 secondi per il failover e 240 secondi per il fallback.

> [!CAUTION]
> Il valore minimo per l'**intervallo di failover** non deve essere inferiore a 90 secondi. Se si imposta un valore inferiore, verrà comunque applicato un intervallo di 90 secondi. Il tempo necessario per il ping tra cluster è di 30 secondi, pertanto un'impostazione inferiore a 90 secondi può causare l'attivazione e disattivazione ciclica sia del server principale che di quello di backup, con un impatto considerevole sulla produzione, in quanto i due server tentano di risolvere lo stato l'uno dell'altro. Un intervallo di meno di 90 secondi non costituisce un tempo sufficiente per determinare se il server principale sia effettivamente non disponibile.

### <a name="web-services"></a>Servizi Web

Per modificare o specificare ulteriori impostazioni per i servizi Web nel pool Front End, modificare o specificare le impostazioni in **Servizi Web interni** e **Servizi Web esterni**.

In **Servizi Web interni** specificare quanto segue:

> [!CAUTION]
> Se si dispone di più di un pool Front-end o di un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile usare **pool01.contoso.com** per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni FQDN deve essere univoco da qualsiasi altro pool di front end, Director o Director.

- Se si seleziona **Sostituisci FQDN**, sarà possibile specificare un FQDN diverso per l'identità dei **Servizi Web interni** nel pool. Per impostazione predefinita, l'impostazione corrisponde al nome corrente definito per il pool Front End.

- Le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite, ovvero la porta 80 per HTTP e la porta 443 per HTTPS, sono le impostazioni più comuni e in genere non devono essere modificate, tranne nel caso di requisiti specifici per l'organizzazione e la progettazione dell'infrastruttura.

In **Servizi Web esterni** specificare quanto segue:

- L'FQDN dei servizi Web esterni. L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.

- Le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite della porta 8080 per HTTP e della porta 4443 per HTTPS sono definite inizialmente. Queste impostazioni vengono modificate per le porte in ascolto in base a quali sono i requisiti per il proxy inverso e per i requisiti di rete esterna. Le porte pubblicate sono impostate su default della porta 80 per HTTP e della porta 443 per HTTPS. Questi valori determinano quali porte verranno ascoltate dal pool per le richieste in arrivo. In genere, non è necessario modificarlo, a meno che non ci sia un conflitto di requisiti di porta nel pool. Sono previste porte pubblicate interne ed esterne che usano gli stessi valori di porta. Non si tratta di un conflitto.

### <a name="mediation-server"></a>Mediation Server

In **Mediation Server** specificare quanto segue:

- Se si sceglie di collocare il Mediation Server nel pool, selezionare la casella di controllo **Mediation Server nella stessa posizione abilitato**. Se si sceglie di non collocare il Mediation Server, non sarà disponibile alcuna impostazione di questa sezione.

- Se si abilita la collocazione del Mediation Server, definire l'intervallo di porte di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.

- I trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

- Se a un Mediation Server è associato più di un trunk, è possibile specificare un trunk predefinito selezionando il gateway e facendo clic su **Rendi predefinito**. Per annullare l'impostazione del gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il pool Front End, vedere [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Server Standard Edition

Per un server Standard Edition, è possibile configurare impostazioni generali, di resilienza, dei servizi Web e del Mediation Server. Per informazioni dettagliate, vedere le sottosezioni riportate di seguito. Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il server Standard Edition, vedere [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Impostazioni generali

È possibile configurare le impostazioni generali seguenti:

- **FQDN**. Si noti che l'FQDN non può essere modificato. Per modificare l'FQDN, è necessario rimuovere e ridefinire il server Standard Edition a cui è associato.

- Selezionare **Usa tutti gli indirizzi IP configurati** o **Limita utilizzo servizio a indirizzi IP selezionati**. Se si sceglie di limitare il servizio agli indirizzi IP definiti, sarà necessario definire l'indirizzo IP primario che verrà usato dal server per tutte le comunicazioni, tranne PSTN. Sarà necessario definire un indirizzo IP separato per l'utilizzo di PSTN. È anche possibile selezionare **Abilita IPv6** per abilitare IPv6 per questo server.

- **Abilita la porta di monitoraggio del bilanciamento del carico hardware**. Selezionare questa casella di controllo e immettere il numero di porta che il dispositivo di bilanciamento del carico hardware userà per monitorare lo stato del server.

- In **Caratteristiche e funzionalità** definire gli ulteriori ruoli che si desidera collocare nel server. È possibile configurare le impostazioni seguenti:

  - **Servizio di conferenza**. Include audio, video e condivisione applicazioni. Dopo avere selezionato questa opzione, è possibile selezionare **Servizi di conferenza telefonica con accesso esterno (PSTN)**. È possibile specificare e definire un gateway PSTN più avanti nelle impostazioni del Mediation Server.

  - **VoIP aziendale**. Consente le chiamate vocali interne tramite IP a telefoni e dispositivi qualificati e ai client Skype for business. Per abilitare le funzionalità di chiamata esterna, è necessario includere un Mediation Server. Per informazioni dettagliate, vedere "Mediation Server" più avanti in questo argomento.

- In **Associazioni** è possibile modificare o specificare quanto segue:

  - Selezionare **Archivio SQL Server** per associare un archivio SQL Server al Front End Server. È inoltre possibile abilitare il mirroring e selezionare un server di controllo del mirroring.

  - **Condivisione file**. Modificare l'archivio file usato dal server Standard Edition. È possibile utilizzare un nuovo archivio file tra quelli già definiti selezionandolo nell'elenco oppure creare un nuovo archivio file facendo clic su **Nuovo**.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

  - **Archiviazione**. Associare un archivio SQL Server per l'archiviazione al server Standard Edition. È possibile usare un archivio già definito selezionando il server nell'elenco oppure specificare un nuovo archivio facendo clic su **Nuovo**.

    > [!IMPORTANT]
    > Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.

  - **Monitoraggio (CDR e metrica QoE)**. Associare un archivio SQL Server per il monitoraggio al server Standard Edition. È possibile usare un Monitoring Server già definito selezionandolo nell'elenco oppure specificare un nuovo Monitoring Server facendo clic su **Nuovo**.

  - **Associa il pool a un server Office Web Apps**. Selezionare questa opzione per associare un server Office Web Apps a un pool Front End. È possibile selezionare un server esistente nell'elenco oppure crearne uno nuovo facendo clic su **Nuovo**.

  - **Associa pool di server perimetrali**. Associare un server perimetrale o un pool di server perimetrali al server Standard Edition. È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.

### <a name="resiliency"></a>Resilienza

La resilienza fornisce al server funzionalità di ripristino di emergenza e disponibilità elevata. Fornendo un server di backup, in caso di malfunzionamento del server principale, quello di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi.

Selezionare nell'elenco il pool Front End o il server Standard Edition che opererà come backup del server. È inoltre possibile impostare intervalli di tempo per il failover e il fallback. Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di una funzione di registrazione con problemi ed è previsto un periodo di tempo per determinare automaticamente se la funzione principale sia di nuovo attiva.

> [!IMPORTANT]
> Nel definire l'intervallo di rilevamento degli errori e l'intervallo di fallback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al fallback se il server non risponde per un breve periodo di tempo. È infatti possibile che il server principale non risponda per brevi periodi a causa del caricamento del pool o dei server. I valori predefiniti per il failover e il fallback sono di 300 secondi e 600 secondi da un pool all'altro oppure da un pool a un server Standard Edition. Nel caso di un Survivable Branch Appliance o di un Survivable Branch Server da un sito a un pool oppure a un server Standard Edition, i valori predefiniti sono di 120 secondi per il failover e 240 secondi per il fallback.

### <a name="web-services"></a>Servizi Web

Per modificare o specificare ulteriori impostazioni per i servizi Web nel server, modificare o specificare le impostazioni in **Servizi Web interni** e **Servizi Web esterni**.

Per **Servizi Web interni** è possibile specificare quanto segue:

- Se si seleziona Sostituisci FQDN, sarà possibile specificare un FQDN diverso per l'identità dei Servizi Web interni nel server. Per impostazione predefinita, l'impostazione corrisponde al nome corrente definito per il server Standard Edition.

- Le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite, ovvero la porta 80 per HTTP e la porta 443 per HTTPS, sono le impostazioni più comuni e in genere non devono essere modificate, tranne nel caso di requisiti specifici per l'organizzazione e la progettazione dell'infrastruttura.

Per **Servizi Web esterni** è possibile specificare quanto segue:

- L'FQDN dei servizi Web esterni. L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.

- Le porte di attesa per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite, ovvero la porta 8080 per HTTP e la porta 4443 per HTTPS, vengono definite inizialmente. È quindi possibile modificarle per le porte di attesa in base ai requisiti del proxy inverso e della rete esterna. Questi valori determinano le porte su cui il server resterà in attesa di richieste in arrivo e in genere non devono essere modificati, tranne in caso di conflitto tra le porte richieste nel server.

### <a name="mediation-server"></a>Mediation Server

Per il **Mediation Server** è possibile specificare quanto segue:

- Se si sceglie di collocare il Mediation Server nel server, selezionare la casella di controllo **Mediation Server nella stessa posizione abilitato**. Se si sceglie di non collocare il Mediation Server, non sarà disponibile alcuna impostazione di questa sezione.

- Se è stata abilitata la collocazione del Mediation Server, definire l'intervallo di porte di attesa nel server per TLS. Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.

- I trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

- Se a un Mediation Server è associato più di un gateway, è possibile specificare un gateway predefinito selezionando il gateway e facendo clic su **Rendi predefinito**. Per annullare l'impostazione del gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il server Standard Edition, vedere [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


