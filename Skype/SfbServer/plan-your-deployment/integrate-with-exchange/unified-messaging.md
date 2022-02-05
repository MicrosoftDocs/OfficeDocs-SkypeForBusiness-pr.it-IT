---
title: Pianificare l'Exchange di messaggistica unificata in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Riepilogo: leggere questo argomento durante la pianificazione dell''integrazione Skype for Business Server con Exchange 2013 o 2016.'
---

# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Pianificare l'Exchange di messaggistica unificata in Skype for Business

**Riepilogo:** Leggere questo argomento durante la pianificazione dell'integrazione Skype for Business Server con Exchange 2013 o 2016.

Skype for Business Server supporta l'integrazione con Exchange messaggistica unificata per combinare la messaggistica vocale e la messaggistica di posta elettronica in un'unica infrastruttura di messaggistica. In Exchange, Exchange messaggistica unificata è uno dei diversi ruoli Exchange server che è possibile installare e configurare.

In Microsoft Exchange Server 2013 e 2016, la messaggistica unificata Exchange viene eseguita come servizio su un server Cassette postali Exchange server Cassette postali. Per Skype for Business Server VoIP aziendale, la messaggistica unificata combina la messaggistica vocale e la messaggistica elettronica in un unico archivio a cui gli utenti possono accedere da un telefono (Outlook Voice Access) o da un computer. Messaggistica unificata e Skype for Business Server insieme per fornire servizi di risposta alle chiamate, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.

> [!NOTE]
> Exchange messaggistica unificata rimane disponibile Skype for Business Server 2019 quando si integra Skype for Business 2019 con Exchange 2013 o Exchange 2016. A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione di messaggistica unificata di Exchange viene de-enfatizzata a favore delle funzionalità Cloud Voicemail e Cloud Operatore automatico.  Per [ulteriori informazioni, vedere Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [Plan for Skype for Business Server and Exchange Server migration](../../../sfbhybrid/hybrid/plan-um-migration.md).


Per il supporto di queste funzionalità in una distribuzione locale Exchange messaggistica unificata, è necessario eseguire una delle operazioni seguenti:

- Microsoft Exchange Server 2010 o service pack più recente (solo Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange la messaggistica unificata nota in precedenza non è più disponibile in Skype for Business Server 2019, che utilizza Sistema telefonico per registrare i messaggi della segreteria telefonica e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per [ulteriori informazioni, vedere Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Funzionalità della messaggistica unificata integrata e Skype for Business Server

Skype for Business Server, VoIP aziendale utilizza l'infrastruttura di messaggistica unificata di Exchange per fornire servizi di risposta alle chiamate, notifica delle chiamate, accesso vocale (inclusa la segreteria telefonica) e operatore automatico.

- **Rispondito alle chiamate** Il rispondimento chiamata è la ricezione di messaggi vocali per conto degli utenti le cui chiamate non hanno risposta o sono occupate. Include la riproduzione di un messaggio di saluto personale, la registrazione di un messaggio e l'invio del messaggio da accodare per il recapito alla cassetta postale dell'utente, archiviata nel server cassette postali Exchange.

    Se un chiamante lascia un messaggio, il messaggio viene instradato alla posta in arrivo dell'utente. Se un chiamante sceglie di non lasciare un messaggio, nella cassetta postale dell'utente viene memorizzata una notifica di chiamata senza risposta. Gli utenti possono quindi accedere alla posta in arrivo utilizzando il client di messaggistica e collaborazione di Microsoft Outlook, Outlook Web Access, la tecnologia Exchange ActiveSync o Outlook Voice Access. L'oggetto e la priorità delle chiamate possono essere visualizzati in modo simile a quello della posta elettronica.

- **Outlook Voice Access** Outlook Voice Access consente a un utente di VoIP aziendale di accedere non solo alla posta vocale, ma anche alla posta in arrivo di Exchange, inclusi posta elettronica, calendario e contatti da un'interfaccia di telefonia. Il numero di accesso del sottoscrittore viene assegnato da un Exchange di messaggistica unificata.

- **Operatore automatico** Operatore automatico è una Exchange di messaggistica unificata che può essere utilizzata per configurare un numero di telefono che gli utenti esterni possono comporre per raggiungere i rappresentanti della società. In particolare, fornisce una serie di prompt vocali che assiste un chiamante esterno nello spostamento in un sistema di menu. L'elenco delle opzioni disponibili viene configurato nel server messaggistica unificata Exchange dall'amministratore Exchange messaggistica unificata.

- **Servizi fax** Exchange messaggistica unificata include funzionalità fax, che consentono agli utenti di ricevere fax in ingresso nelle cassette postali Exchange fax. Per informazioni dettagliate, vedere [Unified Messaging](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) nella Microsoft Exchange Server documentazione.

    > [!NOTE]
    > I servizi fax forniti dal server Messaggistica unificata di Exchange non sono disponibili nelle distribuzioni di Skype for Business Server integrate con Microsoft Exchange Server 2010, Exchange 2010 con il Service Pack più recente, Exchange 2013 o Exchange  2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componenti e topologie per la messaggistica unificata locale in Skype for Business Server

### <a name="exchange-server-components"></a>Componenti di Exchange Server

Per fornire le funzionalità e i servizi di messaggistica unificata di Exchange descritti in Funzionalità di messaggistica unificata integrata e [Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) agli utenti di VoIP aziendale nell'organizzazione, è necessario distribuire un'organizzazione microsoft Exchange  Server Cassette postali e server Accesso client, che ospita le cassette postali degli utenti e fornisce un'unica posizione di archiviazione per la posta elettronica e la segreteria telefonica. Exchange la messaggistica unificata viene eseguita come servizio sui Exchange Cassette postali e Accesso client.

Per informazioni dettagliate Exchange componenti di messaggistica unificata in Microsoft Exchange Server 2010, vedere [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Topologie supportate

È possibile distribuire Skype for Business Server e Exchange messaggistica unificata nella stessa foresta o in più foreste. Se la distribuzione si estende su più foreste, è necessario eseguire i passaggi di Exchange di integrazione per ogni Exchange di messaggistica unificata. Inoltre, è necessario configurare ogni foresta di Microsoft Exchange per considerare attendibile la foresta di Skype for Business Server e la foresta Skype for Business Server per considerare attendibile ogni foresta Exchange messaggistica unificata. Oltre a questo trust tra foreste, le impostazioni Exchange di messaggistica unificata per tutti gli utenti devono essere impostate sugli oggetti utente nella Skype for Business Server foresta.

Skype for Business Server supporta le topologie seguenti per l'integrazione Exchange messaggistica unificata:

- Foresta singola

- Singolo dominio, ovvero foresta singola con un solo dominio. Skype for Business Server, Microsoft Exchange e gli utenti risiedono tutti nello stesso dominio.

- Dominio multiplo, ovvero un dominio radice con uno o più domini figlio. Skype for Business Server e i server Microsoft Exchange vengono distribuiti in domini diversi dal dominio in cui vengono creati gli utenti. Exchange server Messaggistica unificata possono essere distribuiti in domini diversi dal pool Skype for Business Server che supportano.

- Foresta multipla, ovvero foresta di risorse. Skype for Business Server viene distribuito in una singola foresta e quindi gli utenti vengono distribuiti tra più foreste. Gli attributi di Exchange di messaggistica unificata degli utenti devono essere replicati nella Skype for Business Server foresta.

    > [!NOTE]
    > Exchange può essere distribuito in più foreste. Ogni Exchange può fornire Exchange messaggistica unificata agli utenti oppure Exchange messaggistica unificata può essere distribuita nella stessa foresta di Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Linee guida per l'integrazione della messaggistica unificata locale e Skype for Business Server

Di seguito sono riportate le linee guida e le procedure consigliate da prendere in considerazione quando si distribuisce VoIP aziendale:

> [!IMPORTANT]
> Exchange messaggistica unificata supporta IPv6 solo se si utilizza anche UCMA 4.

- Distribuire un Skype for Business Server edizione Standard server o un pool Front End.

- Collaborare con gli amministratori di Exchange per verificare le attività che verranno eseguite da ognuno al fine di assicurare un'integrazione agevole e corretta.

- Distribuire i ruoli Exchange del server Cassette postali in ogni foresta Exchange messaggistica unificata in cui si desidera abilitare gli utenti per la Exchange messaggistica unificata. Per informazioni dettagliate sull'installazione Exchange ruoli del server, vedere la Microsoft Exchange Server documentazione.

    > [!IMPORTANT]
    > Quando Exchange messaggistica unificata, viene configurata per l'utilizzo di un certificato autofirmato. Il certificato autofirmato non consente alla messaggistica unificata di Skype for Business Server e Exchange di considerarsi attendibili l'un l'altro, motivo per cui è necessario richiedere un certificato separato da un'autorità di certificazione attendibile da entrambi i server.

- Se Skype for Business Server e Exchange messaggistica unificata sono installati in foreste diverse, configurare ogni foresta di Exchange in modo da considerare attendibile la foresta di Skype for Business Server e la foresta Skype for Business Server in modo che ritieni attendibile ogni Exchange foresta. Impostare inoltre le impostazioni di messaggistica unificata Exchange degli utenti per gli oggetti utente nella foresta di Skype for Business Server, in genere utilizzando uno script o uno strumento tra foreste, ad esempio Identity Lifecycle Manager (ILM).

- Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.

- Ottenere numeri di telefono validi per Outlook Voice Access e l'operatore automatico.

- Se si utilizza una versione di messaggistica unificata di Exchange precedente a Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinare i nomi per i dial plan URI SIP di messaggistica unificata di Exchange e i dial plan VoIP aziendale.

### <a name="deploying-redundant-exchange-um-servers"></a>Distribuzione di server di messaggistica unificata di Exchange ridondanti

> [!IMPORTANT]
> È consigliabile distribuire almeno due server in cui sono Exchange in esecuzione Exchange servizi di messaggistica unificata per ogni dial plan URI SIP di messaggistica unificata configurato per l'organizzazione. Oltre a fornire una capacità estesa, la distribuzione di server ridondanti garantisce un'elevata disponibilità. In caso di errore del server, Skype for Business Server può essere configurato per il failover su un altro server.

Le configurazioni di esempio seguenti garantiscono resilienza della messaggistica unificata di Exchange.

**Esempio 1: resilienza della messaggistica unificata di Exchange**

![Exchange di resilienza di messaggistica unificata.](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. In caso di un'interruzione della messaggistica unificata di Exchange in Tukwila, i record A DNS (Domain Name System) per i server 1 e 2 devono essere configurati in modo che puntino rispettivamente ai server 3 e 4. In caso di interruzione della messaggistica unificata di Exchange a Dublino, i record A DNS per i server 3 e 4 devono essere configurati in modo che puntino rispettivamente ai server 1 e 2.

> [!NOTE]
> Ad esempio, è inoltre necessario assegnare uno dei seguenti certificati in ogni server Messaggistica unificata di Exchange: utilizzare un certificato con un carattere jolly nel nome alternativo del soggetto (SAN) o inserire il nome di dominio completo (FQDN) di ognuno dei quattro server messaggistica unificata di Exchange nella san.

**Esempio 2: resilienza della messaggistica unificata di Exchange**

![Exchange di resilienza di messaggistica unificata.](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Nell'esempio 2, in condizioni operative standard, i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti Tukwila, tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange a Tukwila, ad esempio, i server 1 e 2 di messaggistica unificata di Exchange devono essere disabilitati e i server 3 e 4 di messaggistica unificata di Exchange devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange di Tukwila venga instradato ai server di Dublino.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata Exchange 2013, vedere [Integrate Exchange 2013 UM with Lync Server](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help). Le informazioni fornite si applicano ugualmente Skype for Business Server.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata Microsoft Exchange Server 2010, vedere:

- [Abilitare la messaggistica unificata Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Disabilitare la messaggistica unificata Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange la messaggistica unificata non è più presente in Exchange 2019, se si dispone di Exchange 2019 e si desidera una funzionalità equivalente, sarà necessario utilizzare il servizio Cloud Voicemail descritto in [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Vedere anche

[Panoramica del processo di distribuzione per l'integrazione della messaggistica unificata locale e Skype for Business](deployment-overview.md)