---
title: Pianificare l'integrazione della messaggistica unificata di Exchange in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: "Riepilogo: esaminare questo argomento durante la pianificazione dell'integrazione di Skype for Business Server con Exchange 2013 o 2016."
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810116"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Pianificare l'integrazione della messaggistica unificata di Exchange in Skype for Business

**Riepilogo:** Leggere questo argomento durante la pianificazione dell'integrazione di Skype for Business Server con Exchange 2013 o 2016.

Skype for Business Server supporta l'integrazione con la messaggistica unificata di Exchange per combinare la messaggistica vocale e la messaggistica di posta elettronica in un'unica infrastruttura di messaggistica. In Exchange, la messaggistica unificata di Exchange è uno dei numerosi ruoli del server Exchange che è possibile installare e configurare.

In Microsoft Exchange Server 2013 e 2016, la messaggistica unificata di Exchange viene eseguita come servizio su un server Cassette postali di Exchange. Per le distribuzioni di Skype for Business Server VoIP aziendale, la messaggistica unificata combina la messaggistica vocale e la messaggistica di posta elettronica in un unico archivio a cui gli utenti possono accedere da un telefono (Outlook Voice Access) o da un computer. La messaggistica unificata e Skype for Business Server lavorano insieme per fornire servizi di risposta alle chiamate, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.

> [!NOTE]
> La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for Business 2019 con Exchange 2013 o Exchange 2016. A causa dei cambiamenti nel supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene de-enfatizzata a favore delle funzionalità cloud voicemail e cloud Operatore automatico.  Per [altre informazioni,](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) vedere Pianificare il servizio Cloud Voicemail e Pianificare [Skype for Business Server Exchange Server migrazione.](../../../sfbhybrid/hybrid/plan-um-migration.md)


Per il supporto di queste funzionalità in una distribuzione di messaggistica unificata di Exchange locale, è necessario eseguire una delle operazioni seguenti:

- Microsoft Exchange Server 2010 o service pack più recente (solo Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> La messaggistica unificata di Exchange come precedentemente noto non è più disponibile in Skype for Business Server 2019, che utilizza Sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Funzionalità della messaggistica unificata integrata e Skype for Business Server

Skype for Business Server, VoIP aziendale utilizza l'infrastruttura di messaggistica unificata di Exchange per fornire servizi di risposta alle chiamate, notifica di chiamata, accesso vocale (inclusa la segreteria telefonica) e operatore automatico.

- **Rispondito di chiamata** Il rispondimento chiamata è la ricezione di messaggi vocali per conto degli utenti le cui chiamate non rispondono o sono occupate. Include la riproduzione di un messaggio di saluto personale, la registrazione di un messaggio e l'invio del messaggio da accodare per il recapito alla cassetta postale dell'utente, archiviato nel server Cassette postali di Exchange.

    Se un chiamante lascia un messaggio, il messaggio viene instradato alla cartella Posta in arrivo dell'utente. Se un chiamante sceglie di non lasciare un messaggio, nella cassetta postale dell'utente viene memorizzata una notifica di chiamata senza risposta. Gli utenti possono quindi accedere alla posta in arrivo utilizzando il client di messaggistica e collaborazione di Microsoft Outlook, Outlook Web Access, la tecnologia Exchange ActiveSync o Outlook Voice Access. L'oggetto e la priorità delle chiamate possono essere visualizzati in modo simile a quello della posta elettronica.

- **Outlook Voice Access** Outlook Voice Access consente a un VoIP aziendale di accedere non solo alla posta vocale, ma anche alla posta in arrivo di Exchange, inclusi posta elettronica, calendario e contatti da un'interfaccia telefonica. Il numero di accesso del sottoscrittore viene assegnato da un amministratore di messaggistica unificata di Exchange.

- **Operatore automatico** L'operatore automatico è una funzionalità di messaggistica unificata di Exchange che può essere utilizzata per configurare un numero di telefono che gli utenti esterni possono comporre per raggiungere i rappresentanti della società. In particolare, fornisce una serie di istruzioni vocali che assistono un chiamante esterno nello spostamento in un sistema di menu. L'elenco delle opzioni disponibili viene configurato sul server Messaggistica unificata di Exchange dall'amministratore di messaggistica unificata di Exchange.

- **Servizi fax** La messaggistica unificata di Exchange include funzionalità fax che consentono agli utenti di ricevere fax in ingresso nelle proprie cassette postali di Exchange. Per informazioni dettagliate, vedere [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) nella Microsoft Exchange Server documentation.

    > [!NOTE]
    > I servizi fax forniti dal server Messaggistica unificata di Exchange non sono disponibili nelle distribuzioni di Skype for Business Server integrate con Microsoft Exchange Server 2010, Exchange 2010 con il Service Pack più recente, Exchange 2013 o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componenti e topologie per la messaggistica unificata locale in Skype for Business Server

### <a name="exchange-server-components"></a>Componenti di Exchange Server

Per fornire le funzionalità e i servizi di messaggistica unificata di Exchange descritti in Funzionalità della messaggistica unificata integrata e [Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) agli utenti di VoIP aziendale nell'organizzazione, è necessario distribuire un server Cassette postali di Microsoft Exchange e un server Accesso client, che ospita le cassette postali degli utenti e fornisce un'unica posizione di archiviazione per la posta elettronica e la segreteria telefonica. La messaggistica unificata di Exchange viene eseguita come servizio sui server Cassette postali e Accesso client di Exchange.

Per informazioni dettagliate sui componenti di messaggistica unificata di Exchange in Microsoft Exchange Server 2010, vedere [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)

### <a name="supported-topologies"></a>Topologie supportate

È possibile distribuire Skype for Business Server e messaggistica unificata di Exchange nella stessa foresta o in più foreste. Se la distribuzione si estende su più foreste, è necessario eseguire i passaggi di integrazione di Exchange per ogni foresta di messaggistica unificata di Exchange. Inoltre, è necessario configurare ogni foresta di Microsoft Exchange per considerare attendibile la foresta di Skype for Business Server e la foresta di Skype for Business Server per considerare attendibile ogni foresta di messaggistica unificata di Exchange. Oltre a questo trust tra foreste, le impostazioni di messaggistica unificata di Exchange per tutti gli utenti devono essere impostate sugli oggetti utente nella foresta di Skype for Business Server.

Skype for Business Server supporta le seguenti topologie per l'integrazione della messaggistica unificata di Exchange:

- Foresta singola

- Singolo dominio, ovvero foresta singola con un solo dominio. Skype for Business Server, Microsoft Exchange e gli utenti risiedono tutti nello stesso dominio.

- Dominio multiplo, ovvero un dominio radice con uno o più domini figlio. I server Skype for Business Server e Microsoft Exchange vengono distribuiti in domini diversi dal dominio in cui vengono creati gli utenti. I server messaggistica unificata di Exchange possono essere distribuiti in domini diversi dal pool di Skype for Business Server che supportano.

- Foresta multipla, ovvero foresta di risorse. Skype for Business Server viene distribuito in una singola foresta e quindi gli utenti vengono distribuiti tra più foreste. Gli attributi di messaggistica unificata di Exchange degli utenti devono essere replicati nella foresta di Skype for Business Server.

    > [!NOTE]
    > Exchange può essere distribuito in più foreste. Ogni organizzazione di Exchange può fornire messaggistica unificata di Exchange agli utenti oppure la messaggistica unificata di Exchange può essere distribuita nella stessa foresta di Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Linee guida per l'integrazione della messaggistica unificata locale con Skype for Business Server

Di seguito sono riportate le linee guida e le procedure consigliate da prendere in considerazione quando si distribuisce VoIP aziendale:

> [!IMPORTANT]
> La messaggistica unificata di Exchange supporta IPv6 solo se si utilizza anche UCMA 4.

- Distribuire un server Skype for Business Server Standard Edition o un pool Front End.

- Collaborare con gli amministratori di Exchange per verificare le attività che verranno eseguite da ognuno al fine di assicurare un'integrazione agevole e corretta.

- Distribuire i ruoli del server Cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si desidera abilitare gli utenti alla messaggistica unificata di Exchange. Per informazioni dettagliate sull'installazione dei ruoli del server exchange, vedere la documentazione Microsoft Exchange Server exchange.

    > [!IMPORTANT]
    > Quando la messaggistica unificata di Exchange è installata, viene configurata per l'utilizzo di un certificato autofirmato. Il certificato autofirmato non consente a Skype for Business Server e alla messaggistica unificata di Exchange di considerarsi attendibili, per questo motivo è necessario richiedere un certificato separato da un'autorità di certificazione attendibile per entrambi i server.

- Se Skype for Business Server e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Skype for Business Server e la foresta di Skype for Business Server per considerare attendibile ogni foresta di Exchange. Inoltre, impostare le impostazioni di messaggistica unificata di Exchange degli utenti sugli oggetti utente nella foresta di Skype for Business Server, in genere utilizzando uno script o uno strumento tra foreste, ad esempio Identity Lifecycle Manager (ILM).

- Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.

- Ottenere numeri di telefono validi per Outlook Voice Access e l'operatore automatico.

- Se si utilizza una versione della messaggistica unificata di Exchange precedente a Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinare i nomi dei dial plan URI SIP di messaggistica unificata di Exchange e VoIP aziendale dial plan.

### <a name="deploying-redundant-exchange-um-servers"></a>Distribuzione di server di messaggistica unificata di Exchange ridondanti

> [!IMPORTANT]
> Si consiglia di distribuire almeno due server su cui sono in esecuzione i servizi di messaggistica unificata di Exchange per ogni dial plan URI SIP di messaggistica unificata di Exchange configurato per l'organizzazione. Oltre a fornire capacità espansa, la distribuzione di server ridondanti offre disponibilità elevata. In caso di errore del server, Skype for Business Server può essere configurato per il failover su un altro server.

Le configurazioni di esempio seguenti garantiscono resilienza della messaggistica unificata di Exchange.

**Esempio 1: resilienza della messaggistica unificata di Exchange**

![Diagramma della resilienza della messaggistica unificata di Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. In caso di interruzione della messaggistica unificata di Exchange in Tukwila, i record A DNS (Domain Name System) per i server 1 e 2 devono essere configurati in modo da puntare rispettivamente ai server 3 e 4. In caso di interruzione della messaggistica unificata di Exchange a Dublino, i record A DNS per i server 3 e 4 devono essere configurati in modo da puntare rispettivamente ai server 1 e 2.

> [!NOTE]
> Ad esempio 1, è inoltre necessario assegnare uno dei seguenti certificati su ogni server Messaggistica unificata di Exchange: utilizzare un certificato con un carattere jolly nel nome alternativo del soggetto (SAN) o inserire il nome di dominio completo (FQDN) di ognuno dei quattro server messaggistica unificata di Exchange nel san.

**Esempio 2: resilienza della messaggistica unificata di Exchange**

![Diagramma della resilienza della messaggistica unificata di Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Nell'esempio 2, in condizioni operative standard, i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti Tukwila, tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange a Tukwila, ad esempio, i server 1 e 2 di messaggistica unificata di Exchange devono essere disabilitati e i server 3 e 4 di messaggistica unificata di Exchange devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange di Tukwila venga instradato ai server di Dublino.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere Integrare la messaggistica unificata di [Exchange 2013 con Lync Server.](https://go.microsoft.com/fwlink/p/?LinkId=265372) Le informazioni fornite si applicano ugualmente a Skype for Business Server.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata Microsoft Exchange Server 2010, vedere:

- [Abilitazione della messaggistica unificata in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Disabilitare la messaggistica unificata in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

La messaggistica unificata di Exchange non è più presente in Exchange 2019, se si dispone di Exchange 2019 e si desidera una funzionalità equivalente, sarà necessario utilizzare il servizio Cloud Voicemail descritto in [Plan Cloud Voicemail service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)


## <a name="see-also"></a>Vedere anche

[Panoramica del processo di distribuzione per l'integrazione della messaggistica unificata locale con Skype for Business](deployment-overview.md)
