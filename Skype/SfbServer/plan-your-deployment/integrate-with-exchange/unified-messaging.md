---
title: Pianificare l'integrazione della messaggistica unificata di Exchange in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Riepilogo: rivedere questo argomento mentre si prevede di integrare Skype for Business Server con Exchange 2013 o 2016.'
ms.openlocfilehash: 3b71dd740440aeab37919bb94ef98eaeb83d4d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194932"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Pianificare l'integrazione della messaggistica unificata di Exchange in Skype for business

**Riepilogo:** Esaminare questo argomento durante la pianificazione dell'integrazione di Skype for Business Server con Exchange 2013 o 2016.

Skype for Business Server supporta l'integrazione con la messaggistica UNIFICAta di Exchange per combinare la messaggistica vocale e la messaggistica di posta elettronica in un'unica infrastruttura di messaggistica. In Exchange la messaggistica unificata di Exchange è uno dei diversi ruoli di Exchange Server che è possibile installare e configurare.

In Microsoft Exchange Server 2013 e 2016 la messaggistica unificata di Exchange viene eseguita come servizio in un server cassette postali di Exchange. Per le distribuzioni vocali di Skype for Business Server Enterprise, la messaggistica unificata combina la messaggistica vocale e la messaggistica di posta elettronica in un singolo archivio a cui gli utenti possono accedere da un telefono (Outlook Voice Access) o da un computer. La messaggistica unificata e Skype for Business Server collaborano per fornire servizi di segreteria telefonica, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.

> [!NOTE]
> La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for business 2019 con Exchange 2013 o Exchange 2016. A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene sottolineata a favore delle caratteristiche del cloud voicemail e dell'operatore automatico cloud.  Per altre informazioni, Vedi pianificare il servizio per la [segreteria cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [pianificare Skype for Business Server e Exchange Server Migration](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Per supportare queste funzionalità in una distribuzione di messaggistica unificata di Exchange locale, è necessario eseguire una delle operazioni seguenti:

- Microsoft Exchange Server 2010 o Service Pack più recente (solo Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (solo Skype for Business Server 2019)

> [!NOTE]
> La messaggistica unificata di Exchange, come precedentemente nota, non è più disponibile in Skype for Business Server 2019, che usa il sistema telefonico per registrare i messaggi della segreteria telefonica e quindi abbandonare la registrazione nella cassetta postale di Exchange dell'utente. Per altre informazioni, vedere [pianificare il servizio di segreteria cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Caratteristiche della messaggistica unificata integrata e di Skype for Business Server

Skype for Business Server, Enterprise Voice usa l'infrastruttura di messaggistica UNIFICAta di Exchange per fornire le risposte alle chiamate, le notifiche delle chiamate, l'accesso vocale (inclusi i messaggi vocali) e i servizi di operatore automatico.

- **Segreteria** telefonica La segreteria telefonica è la ricezione di messaggi vocali per conto degli utenti le cui chiamate non rispondono o sono occupate. Include la riproduzione di un saluto personale, la registrazione di un messaggio e l'invio del messaggio in coda per il recapito alla cassetta postale dell'utente, archiviato nel server cassette postali di Exchange.

    Se un chiamante lascia un messaggio, il messaggio viene instradato alla posta in arrivo dell'utente. Se un chiamante sceglie di non uscire da un messaggio, nella cassetta postale dell'utente viene archiviata una notifica di chiamata senza risposta. Gli utenti possono quindi accedere alla posta in arrivo usando il client di messaggistica e collaborazione di Microsoft Outlook, Outlook Web Access, la tecnologia Exchange ActiveSync o Outlook Voice Access. L'oggetto e la priorità delle chiamate possono essere visualizzati in modo simile a quello del messaggio di posta elettronica.

- **Outlook Voice Access** Outlook Voice Access consente a un utente di VoIP aziendale di accedere non solo alla segreteria telefonica, ma anche alla posta in arrivo di Exchange, inclusi posta elettronica, calendario e contatti da un'interfaccia di telefonia. Il numero di accesso del Sottoscrittore viene assegnato dall'amministratore della messaggistica unificata di Exchange.

- **Operatore automatico** Operatore automatico è una funzionalità di messaggistica unificata di Exchange che può essere usata per configurare un numero di telefono che gli utenti esterni possono chiamare per raggiungere i rappresentanti della società. In particolare, fornisce una serie di richieste vocali che assistono un chiamante esterno nell'esplorazione di un sistema di menu. L'elenco delle opzioni disponibili è configurato nel server Messaggistica unificata di Exchange dall'amministratore di messaggistica unificata

- **Servizi fax** La messaggistica unificata di Exchange include le caratteristiche fax, che consentono agli utenti di ricevere i fax in arrivo nelle cassette postali di Exchange. Per informazioni dettagliate, vedere [messaggistica unificata](https://go.microsoft.com/fwlink/p/?linkId=135652) nella documentazione di Microsoft Exchange Server.

    > [!NOTE]
    > I servizi fax forniti dal server Messaggistica unificata di Exchange non sono disponibili nelle distribuzioni di Skype for Business Server integrate con Microsoft Exchange Server 2010, Exchange 2010 con il Service Pack più recente, Exchange 2013 o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componenti e topologie per la messaggistica unificata locale in Skype for Business Server

### <a name="exchange-server-components"></a>Componenti di Exchange Server

Per specificare le caratteristiche e i servizi di messaggistica unificata di Exchange descritti in [funzionalità di messaggistica unificata integrata e Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) per gli utenti di VoIP aziendale dell'organizzazione, è necessario distribuire un server cassette postali di Microsoft Exchange e un accesso client Server, che ospita le cassette postali degli utenti e offre una posizione di archiviazione unica per la posta elettronica e la segreteria telefonica. La messaggistica unificata di Exchange viene eseguita come servizio nella cassetta postale di Exchange e nei server Accesso client.

Per informazioni dettagliate sui componenti di messaggistica unificata di Exchange in Microsoft Exchange Server 2010, vedere [distribuzione della messaggistica unificata di Exchange locale per consentire l'anteprima della segreteria telefonica di Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologie supportate

È possibile distribuire Skype for Business Server e messaggistica unificata di Exchange nella stessa foresta o in più foreste. Se la distribuzione si estende su più foreste, è necessario eseguire la procedura di integrazione di Exchange per ogni foresta di messaggistica unificata di Exchange. Inoltre, devi configurare ogni foresta di Microsoft Exchange per considerare attendibile la foresta di Skype for Business Server e la foresta di Skype for Business Server per considerare attendibile ogni foresta di messaggistica unificata di Exchange. Oltre a questo trust tra insiemi di strutture, le impostazioni di messaggistica unificata di Exchange per tutti gli utenti devono essere impostate sugli oggetti utente nella foresta di Skype for Business Server.

Skype for Business Server supporta le topologie seguenti per l'integrazione di messaggistica unificata di Exchange:

- Singola foresta

- Singolo dominio, ovvero una singola foresta con un singolo dominio. Skype for Business Server, Microsoft Exchange e tutti gli utenti si trovano nello stesso dominio.

- Più domini, ovvero un dominio radice con uno o più domini figlio. Skype for Business Server e i server di Microsoft Exchange vengono distribuiti in diversi domini dal dominio in cui si creano utenti. I server di messaggistica unificata di Exchange possono essere distribuiti in diversi domini dal pool di Skype for Business Server supportati.

- Più insiemi di strutture, ovvero foresta delle risorse. Skype for Business Server è distribuito in una singola foresta e quindi gli utenti vengono distribuiti in più foreste. Gli attributi di messaggistica unificata di Exchange degli utenti devono essere replicati nella foresta di Skype for Business Server.

    > [!NOTE]
    > Exchange può essere distribuito in più foreste. Ogni organizzazione di Exchange può specificare la messaggistica unificata di Exchange per gli utenti oppure la messaggistica unificata di Exchange può essere distribuita nella stessa foresta di Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Linee guida per l'integrazione della messaggistica unificata locale e di Skype for Business Server

Di seguito sono riportate le linee guida e le procedure consigliate per la distribuzione di VoIP aziendale:

> [!IMPORTANT]
> La messaggistica unificata di Exchange supporta IPv6 solo se si usa anche UCMA 4.

- Distribuire un server di Skype for Business Server Standard Edition o un pool Front-end.

- Collaborare con gli amministratori di Exchange per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione corretta e efficace.

- Distribuire i ruoli del server cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si vuole abilitare gli utenti per la messaggistica unificata di Exchange. Per informazioni dettagliate sull'installazione dei ruoli di Exchange Server, vedere la documentazione di Microsoft Exchange Server 2013.

    > [!IMPORTANT]
    > Quando è installata la messaggistica unificata di Exchange, è configurata per l'uso di un certificato autofirmato. Il certificato autofirmato non consente a Skype for Business Server e alla messaggistica unificata di Exchange di avere fiducia tra loro, ed è per questo che è necessario richiedere un certificato distinto da un'autorità di certificazione attendibile per entrambi i server.

- Se Skype for Business Server e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Skype for Business Server e la foresta del server Skype for business per considerare attendibile ogni foresta di Exchange. Inoltre, imposta le impostazioni di messaggistica unificata di Exchange degli utenti negli oggetti utente nella foresta di Skype for Business Server, in genere usando uno script o uno strumento tra insiemi di strutture, ad esempio ILM (Identity Lifecycle Manager).

- Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.

- Ottenere i numeri di telefono validi per Outlook Voice Access e l'operatore automatico.

- Se si usa una versione di messaggistica unificata di Exchange precedente a Microsoft Exchange Server 2010 Service Pack 1 (SP1), i nomi delle coordinate per i dial plan di messaggistica unificata di Exchange UM e i piani per le chiamate vocali aziendali.

### <a name="deploying-redundant-exchange-um-servers"></a>Distribuzione di server Messaggistica unificata di Exchange ridondanti

> [!IMPORTANT]
> È consigliabile distribuire un minimo di due server in cui i servizi di messaggistica unificata di Exchange sono in esecuzione per ogni dial plan di messaggistica unificata di Exchange che si configura per l'organizzazione. Oltre a fornire capacità espansa, la distribuzione di server ridondanti offre una disponibilità elevata. In caso di errore del server, Skype for Business Server può essere configurato per il failover su un altro server.

Le configurazioni di esempio seguenti garantiscono la resilienza della messaggistica unificata di Exchange.

**Esempio 1: resilienza della messaggistica unificata di Exchange**

![Diagramma resilienza messaggistica unificata di Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino. In caso di interruzione della messaggistica unificata di Exchange in Tukwila, il DNS (Domain Name System) record per i server 1 e 2 deve essere configurato in modo che punti rispettivamente ai server 3 e 4. In caso di interruzione della messaggistica unificata di Exchange in Dublin, è necessario configurare i record DNS per i server 3 e 4 in modo che puntino rispettivamente ai server 1 e 2.

> [!NOTE]
> Ad esempio 1, devi anche assegnare uno dei seguenti certificati in ogni server Messaggistica unificata di Exchange: usare un certificato con un carattere jolly nel nome alternativo soggetto (SAN) o inserire il nome di dominio completo (FQDN) di ognuno dei quattro server di messaggistica unificata di Exchange nella SAN.

**Esempio 2: resilienza della messaggistica unificata di Exchange**

![Diagramma resilienza messaggistica unificata di Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Nell'esempio 2, in condizioni operative ordinarie i server Messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti di Tukwila; Tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange in Tukwila, ad esempio, i server di messaggistica unificata di Exchange 1 e 2 devono essere disabilitati e i server di messaggistica unificata di Exchange 3 e 4 devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange venga Tukwila ai server di Dublino.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere integrare la messaggistica UNIFICAta di [exchange 2013 con Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Le informazioni fornite si applicano ugualmente a Skype for Business Server.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Microsoft Exchange Server 2010, vedere:

- [Abilitare la messaggistica unificata in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Disabilitare la messaggistica unificata in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

La messaggistica unificata di Exchange non è più presente in Exchange 2019, se si dispone di Exchange 2019 e si vogliono funzionalità equivalenti, sarà necessario usare il servizio cloud Voicemail descritto in [servizio cloud Voicemail](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Vedere anche

[Panoramica del processo di distribuzione per l'integrazione della messaggistica unificata locale e Skype for business](deployment-overview.md)
