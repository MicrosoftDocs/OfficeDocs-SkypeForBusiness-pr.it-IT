---
title: Supporto per la migrazione della messaggistica unificata online di Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft sta ritirando il servizio Exchange Unified Messaging Online (ExchUMO) entro il 28 febbraio 2020. Questo articolo riepiloga le informazioni che i clienti interessati devono conoscere e fare per pianificare la continuità aziendale.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676368"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Supporto per la migrazione della messaggistica unificata online di Exchange

> [!IMPORTANT]
> **Il servizio Messaggistica unificata in Exchange Online non è supportato a partire dal 28 febbraio 2020, 17:00 ora del Pacifico. È stata eseguita la migrazione di tutti gli account della segreteria telefonica al servizio Cloud Voicemail da Microsoft. Il traffico rimanente dell'operatore automatico non verrà monitorato e potrebbe essere interrotto in qualsiasi momento.**

In riferimento [all'annuncio dell'8](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) febbraio 2019, Microsoft sta ritirando il servizio Exchange Unified Messaging Online (ExchUMO) entro il 28 febbraio 2020. Questo articolo offre un riepilogo di ciò che i clienti interessati devono conoscere e fare per pianificare la continuità aziendale.

ExchUMO viene distribuito dai clienti per i servizi di integrazione di segreteria telefonica, operatore automatico, coda di chiamata e fax. Microsoft prevede di aiutare i clienti a eseguire la migrazione a servizi Sistema telefonico che supportano già migliaia di clienti in Skype for Business Online e Microsoft Teams.

La segreteria telefonica è principalmente una migrazione guidata da Microsoft; il coinvolgimento dell'amministratore e/o l'investimento potrebbero essere necessari per un subset di clienti. L'operatore automatico è una migrazione guidata dall'amministratore; sarà necessario ricreare gli alberi dell'operatore automatico ExchUMO esistenti nel servizio cloud dell'operatore automatico cloud. I clienti che utilizzano una delle funzionalità ExchUMO con un PBX di terze parti non verranno migrati ai servizi cloud Skype perché non supportano sistemi PBX di terze parti. In [questo blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853) è stato annunciato un piano di ritiro per il supporto di terze parti e i clienti in questo modello di distribuzione possono eseguire la migrazione degli utenti a una delle piattaforme/servizi di comunicazione unificata di Microsoft o acquisire una soluzione di segreteria telefonica e/o operatore automatico di terze parti per questi utenti. L'integrazione fax non è supportata nei servizi basati sul cloud; i clienti dovranno eseguire la migrazione a una soluzione di terze parti.

## <a name="who-is-affected"></a>Who è interessato?

I clienti che usano una delle funzionalità seguenti del servizio Exchange Unified Messaging Online sono interessati:

- Servizio di segreteria telefonica
- Servizio Operatore automatico
- Servizio accodamento chiamate
- Integrazione fax

> [!Note]
> I clienti che usano una qualsiasi delle Exchange Server locali con messaggistica unificata non sono interessati.

Altre informazioni sull'impatto dell'esperienza utente e amministratore [nell'impatto sull'esperienza utente](#user-experience-impact).

## <a name="migration-plan-overview"></a>Panoramica del piano di migrazione

Microsoft ha identificato varie distribuzioni dei clienti che utilizzano funzionalità di ExchUMO e aiuterà i clienti a eseguire la migrazione in base al piano seguente.

|Gruppo di clienti |Sequenza temporale  |Dettagli  |
|---------|---------|---------|
|Clienti pronti per la migrazione<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Messaggi vocali</ul>   |   Marzo - Maggio 2019  |Esempi:<ul><li>    Clienti con distribuzione e utilizzo semplici della segreteria telefonica<li>Clienti con tutti i requisiti stabiliti per l'esecuzione della migrazione da parte di Microsoft<ul>|
|Clienti con prerequisiti<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Messaggi vocali<li>Operatore automatico<li>Coda di chiamate</ul> |  Maggio - Dicembre 2019 |Esempi: <br><ul><li>La configurazione ibrida non è completa<li>I numeri PSTN ibridi non sono configurati</ul>|
|Clienti che richiedono il coinvolgimento dell'amministratore & l'investimento dei clienti<br><br>Funzionalità di cui eseguire la migrazione:<ul><li>Segreteria telefonica<li>Operatore automatico<li>Code delle chiamate<li>Integrazione fax</ul>| Entro febbraio 2020  | Esempi: <br><ul><li>Il servizio ExchUMO viene utilizzato da PBX di terze parti<li>Clienti con requisiti di accesso sottoscrittore PSTN<li>Clienti su SFB 2010 (non supportato)<li>Integrazione fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Linee guida per la migrazione della segreteria telefonica

### <a name="get-informed"></a>Ottenere informazioni

Acquisire familiarità con [l'annuncio del blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e questo articolo per pianificare una migrazione senza problemi per gli utenti. Vedere [Controllare Skype for Business segreteria telefonica e le opzioni](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) per informazioni dettagliate sulle funzionalità Sistema telefonico Voicemail.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Stabilire una topologia ibrida Skype for Business

Se non è stata stabilita una topologia ibrida Skype for Business, è necessario eseguire questa operazione per consentire una migrazione senza problemi degli utenti della segreteria telefonica. Per altri dettagli, vedere [Configurare Skype for Business ibrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md).

> [!Note]
> Non è necessario eseguire la migrazione online degli utenti per la migrazione del servizio di segreteria telefonica. Tuttavia, per consentire agli utenti locali di sfruttare Sistema telefonico servizio di segreteria telefonica, è necessario stabilire una topologia ibrida.

### <a name="plan-your-auto-attendant-migration"></a>Pianificare la migrazione dell'operatore automatico

Gli amministratori possono iniziare a eseguire la migrazione degli operatori automatici da ExchUMO all'operatore automatico cloud in qualsiasi momento. Per altri dettagli, vedere [Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft continua a offrire funzionalità aggiuntive di operatore automatico che i clienti potrebbero considerare necessarie per la migrazione. Gli amministratori devono valutare il set di funzionalità ed eseguire la migrazione delle istanze dell'operatore automatico di conseguenza. Per un confronto tra elenchi di funzionalità, vedere la [matrice di funzionalità ExchUMO e Servizi basati sul cloud di Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Pianificare la convalida e il test post-migrazione della segreteria telefonica

La migrazione della segreteria telefonica è gestita da Microsoft. Gli amministratori non devono eseguire alcuna operazione, dato che viene stabilita la topologia ibrida prerequisita. Microsoft esegue la convalida e i test necessari per assicurarsi che la migrazione della segreteria telefonica degli utenti non venga interrotta. Gli amministratori sono invitati a eseguire test e convalida dalla loro parte. Vedere [Piano di test suggerito e convalida post-migrazione per gli amministratori](#suggested-test-plan-and-post-migration-validation-for-admins) per un piano di test consigliato.

> [!Note]
> Lync Server 2010 non è supportato. Se si è in una distribuzione server 2010, è consigliabile pianificare un aggiornamento del server o valutare la migrazione degli utenti a Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorare il Centro notifiche Amministrazione

Vedere un avviso nel Centro notifiche Amministrazione con altri dettagli e una sequenza temporale relativa alla migrazione degli utenti. Le notifiche vengono inviate almeno 30 giorni prima del periodo di migrazione.

> [!Note]
> Se è stata ricevuta una notifica con la sequenza temporale di migrazione degli utenti e si vuole posticipare la migrazione per un motivo critico per l'azienda, è possibile farlo contattando supporto tecnico Microsoft. Non è possibile posticipare la migrazione oltre la data di ritiro del 28 febbraio 2020. Per i clienti che potrebbero avere altre domande, contattare il team dell'account o supporto tecnico Microsoft. I clienti che usano già Microsoft 365 o Office 365 possono inviare un caso di supporto tramite il interfaccia di amministrazione di Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Valutare la possibilità di acconsentire esplicitamente a una migrazione pianificata

È possibile acconsentire esplicitamente a una migrazione pianificata del servizio Voicemail alla CVM. Prima di acconsentire esplicitamente, esaminare i dettagli di questo articolo, in particolare le sezioni seguenti:

- Passaggi di migrazione (questa sezione)
- Matrice di funzionalità dei servizi basati sul cloud di Azure e ExchUMO
- Impatto sull'esperienza utente

Quando si sceglie una migrazione gestita, non si riceverà una notifica di 30 giorni prima della migrazione nel centro messaggi del portale di amministrazione Microsoft 365.

Per acconsentire esplicitamente a una migrazione pianificata, inviare una richiesta di posta elettronica dall'indirizzo di posta elettronica dell'amministratore a [cvm@microsoft.com](mailto:cvm@microsoft.com) con le informazioni seguenti:

- Data preferita (martedì): le onde di migrazione vengono eseguite ogni martedì. Selezionare una data di martedì che non sia successiva al 3/12/2019.
 
- ID tenant: numero di 32 caratteri in questo formato 0046728c-688a-4472-a38f-098fec60ac6x. È possibile trovare l'ID tenant nel portale di amministrazione Microsoft 365 in Azure AD o usando il cmdlet di PowerShell seguente:`Get-CsTenant | Select ObjectId`

Una volta eseguita la migrazione del tenant, si riceverà una conferma tramite posta elettronica.

## <a name="auto-attendant-migration-guidelines"></a>Linee guida per la migrazione dell'operatore automatico

Microsoft 365 e Office 365 amministratori dell'organizzazione devono ricreare gli operatori automatici Exchange UM Online nel servizio Operatore automatico cloud Microsoft e passare loro i numeri di telefono locali prima della data di ritiro del servizio UMO Exchange del 28 febbraio 2020. Questa è la linea guida consigliata per eseguire correttamente la migrazione e il test dei nuovi operatori automatici cloud. Se si dispone di un numero elevato di operatori automatici, è possibile usare gli [script di migrazione dell'operatore automatico di messaggistica unificata Exchange per](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) semplificare la migrazione in blocco degli operatori automatici.

### <a name="auto-attendant-setup"></a>Configurazione dell’operatore automatico

È consigliabile avviare la configurazione dei nuovi operatori automatici in anticipo per evitare problemi dell'ultimo minuto e acquisire familiarità con la funzionalità e l'esperienza del servizio Operatore automatico cloud. Per gli operatori automatici che richiedono una o più funzionalità gap, è possibile creare e testare gli operatori automatici quando le funzionalità gap sono disponibili per la preparazione per la distribuzione. Per altre informazioni sulle funzionalità gap, vedere [l'appendice](#appendix).

1. Usare i cmdlet UMO Exchange per esportare la configurazione degli operatori automatici esistenti usando [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Usare il cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell per esportare i file multimediali di saluto (se usati) e convertirli in formato .mp3.

3. Seguire le istruzioni in [Pianificare gli operatori automatici cloud](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant) per creare operatori automatici usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

4. Esaminare i messaggi di saluto se le opzioni di menu sono state modificate.

5. Configurare i trasferimenti ai response group usando la soluzione alternativa "Trasferimento di chiamate dell'operatore automatico a PSTN" nella sezione [Problemi noti](#known-issues) di questo articolo.  

6. Testare i nuovi operatori automatici chiamandoli internamente o assegnando un numero di telefono di test.  

### <a name="cutover"></a>Completa

1. Passare dai numeri di telefono Exchange operatori automatici UMO ai nuovi operatori automatici.
2. Spostare l'URI SIP dall'oggetto contatto all'account della risorsa.
3. Testare e convalidare gli operatori automatici usando i nuovi numeri di telefono assegnati.

## <a name="appendix"></a>Appendice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice di funzionalità dei servizi basati sul cloud di Azure e ExchUMO

| Servizio | Livello di funzionalità | Funzionalità | Note  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Funzionalità del servizio| Supporto di PBX di terze parti    | Inclusione di tutte le funzionalità fornite a PBX di terze parti, ad esempio MWI (Indicatore di attesa messaggi) tramite messaggi di notifica SIP da Exchange messaggistica unificata online | N   | Y    |
| VM | Funzionalità del servizio  | Supporto Skype for Business Server   |  | Y | Y    |
| VM | Funzionalità del servizio | Supporto Microsoft Teams|  | Y | N    |
| VM | Funzionalità del servizio | eDiscovery e blocco  | Per sicurezza e conformità  | Y | Y    |
| VM | Funzionalità del servizio | Supporto delle regole di Exchange | Per sicurezza e conformità  | Y | Y    |
| VM | Funzionalità utente | Accesso con accesso remoto PSTN  | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Delegato  | messaggio di posta elettronica di chiamata senza risposta  | N | Y    |
| VM | Funzionalità utente | Outlook Voice Access PSTN   | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Accesso tramite un endpoint autenticato | Chiamata del servizio di segreteria telefonica per l'ascolto dei messaggi vocali e la modifica delle impostazioni della segreteria telefonica| Y | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la segreteria telefonica   |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare il messaggio di saluto personale  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per creare un messaggio di saluto OOF  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare la lingua predefinita  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per sovrascrivere il messaggio di saluto predefinito con TTS  |  | Y | N    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (dispositivo autenticato) |  | Y | Y    |
| VM | Funzionalità utente | Registrare i messaggi di saluto personali (PSTN) — riprodurre al telefono |  | N | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la trascrizione |  | N | Y    |
| VM | Funzionalità utente | Trascrizione  |  | Y | Y    |
| VM | Funzionalità utente | MWI (Indicatore di messaggi in attesa) tramite messaggi di notifica SIP |  | N | Y    |
| VM | Funzionalità utente | Formato di file audio MP3 in Outlook    |  | Y | Y    |
| VM | Funzionalità utente | Controllo di gioco a velocità variabile |  | Y | Y    |
| VM | Funzionalità utente | Inoltrare una segreteria telefonica  | Inoltrare una segreteria telefonica ricevuta ad altri utenti | Y | Y    |
| VM | Funzionalità utente | Invio di un messaggio vocale a un gruppo di utenti  |Trasmissione della segreteria telefonica   | N | Y   |
| VM | Funzionalità utente | Notifica tramite segreteria telefonica tramite SMS    | Gli utenti possono ricevere un SMS quando hanno una nuova segreteria telefonica    | N | Y    |
| VM | Funzionalità utente | Lingue di saluto supportate | Dettagli qui: [Che cosa sono gli operatori automatici cloud?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | Funzionalità utente | Regole di ricezione chiamata |  | Y | Y    |
| VM | Funzionalità utente | Riproduci sul telefono (PSTN) - per riprodurre il messaggio | Chiamami nella mia cella per ascoltare il messaggio vocale  | N | Y    |
| VM | Funzionalità utente | Riproduci sul telefono (autenticazione) - per riprodurre il messaggio | Chiamami nel dispositivo autenticato  | N | Y    |
| VM | Funzionalità utente | Cassetta postale condivisa tra più utenti |  | Y | Y    |
| VM | Funzionalità del chiamante  | Esperienza del chiamante : segreteria telefonica protetta | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come protetto| N | Y    |
| VM | Funzionalità del chiamante  | Esperienza del chiamante : segreteria telefonica privata | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come privato  | N | Y    |
| VM | Funzionalità del chiamante  | Rilevamento del silenzio   |  | N | Y    |
| VM | Funzionalità Tenant-Admin | Segreteria telefonica protetta a livello di server    | Tenant-admin può configurare una regola a livello di servizio per contrassegnare la segreteria telefonica in ingresso come protetta | Y | Y    |
| VM | Funzionalità Tenant-Admin | Modificare il limite di tempo di registrazione  |     | Y | Y    |
| VM | Funzionalità Tenant-Admin | Timeout di rilevamento del silenzio delle modifiche    |  | N/D    | Y    |
| VM | Funzionalità Tenant-Admin | Modificare il numero di errori di input | CVM: hardcoded to 3 | N | Y    |
| VM | Funzionalità Tenant-Admin | Modificare la lingua predefinita |  | Y | Y    |
| VM | Funzionalità Tenant-Admin | Disabilitare/abilitare la trascrizione |  | Y | Y    |
| VM | Funzionalità Tenant-Admin | Disabilitare/abilitare la notifica di chiamata senza risposta |  | N | Y    |
| VM | Funzionalità Tenant-Admin | Consenti a Microsoft di migliorare l'anteprima della casella vocale    |  | Y | Y    |
| VM | Funzionalità Tenant-Admin | Personalizzare il messaggio di testo per gli utenti abilitati|  | N/D    | Y    |
| VM | Funzionalità Tenant-Admin | Mascheramento volgare della trascrizione|  | Y | N    |
| VM | Funzionalità Tenant-Admin | Criteri di segreteria telefonica    |   | Y | Y    |
| VM | Funzionalità Tenant-Admin | Amministrazione del portale Web   |  | CY19   | Y    |
| VM | Funzionalità Tenant-Admin | PowerShell   |  | Y | Y    |
| Messaggistica unificata | Funzionalità utente | Indicatore di messaggi in attesa (MWI) su telefoni certificati Skype for Business   |Può essere fornito dal partner telefonico  | No | Sì    |
| AA | Funzionalità del servizio | AA supporta PBX di terze parti    |  | N | Y    |
| AA | Funzionalità del servizio | Supporto Skype for Business Server   |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto Microsoft Teams|  | Y | N    |
| AA | Funzionalità del servizio | Composizione per nome, input DTMF    |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione per nome, input vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto per più lingue | Dettagli della lingua qui: [Che cosa sono gli operatori automatici cloud?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento all'operatore, al CQ o a un utente |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN internamente (DID RNL)  |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN esternamente  |  | Vedere la sezione Problemi noti di seguito | Y    |
| AA | Funzionalità del servizio | Ore lavorative |  | Y | Y    |
| AA | Funzionalità del servizio | Opzioni di menu | Opzioni di menu IVR  | Y | Y    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN cloud ad AA |  | Y | N    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN locale ad AA  |  | Y | Y    |
| AA | Funzionalità del servizio | Selezione utente personalizzata  | Abilitazione dei chiamanti per raggiungere un elenco personalizzato di utenti dell'organizzazione| Y | Y    |
| AA | Funzionalità del servizio | Trattamento post-orario e festività  |  | Y | Y    |
| AA | Funzionalità del servizio | Messaggio di saluto personalizzato con sintesi vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione del numero di interno   | Per raggiungere un utente, comporre l'estensione  | Y   | Y    |
| AA | Funzionalità del servizio | Cassetta postale per consentire ai chiamanti AA di lasciare un messaggio    |  | Y   | Y    |
| AA | Funzionalità del servizio | Più assegnazioni di numeri PSTN a un AA|  | Y | Y    |
| AA | Funzionalità Tenant-Admin | Amministrazione del portale Web   |  | Y | N    |
| AA | Funzionalità Tenant-Admin | Cmdlet di PowerShell  |  | Y | Y    |
| Fax| Funzionalità del servizio | Integrazione fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Piano di test consigliato e convalida post-migrazione per gli amministratori

Per verificare che gli utenti siano stati migrati a Cloud Voicemail, lasciare una segreteria telefonica a un utente e controllare il corpo del messaggio in Outlook. Cloud Voicemail messaggi hanno un piè di pagina che legge:

"Grazie per aver usato la trascrizione! Se non vedi una trascrizione sopra, è perché la qualità audio non era abbastanza chiara da trascrivere."

Quando si testa la funzionalità della segreteria telefonica dopo la migrazione degli utenti, assicurarsi di considerare gli scenari seguenti:

- Convalidare l'accesso alla segreteria telefonica in tutti i tipi di endpoint dell'organizzazione, ad esempio app e telefoni IP.
- Verificare con gli utenti di esempio che i messaggi di saluto personalizzati configurati vengano riprodotti ai chiamanti.
- Se l'organizzazione ha un requisito legale o di conformità per disabilitare la trascrizione per gli utenti, assicurarsi che sia disabilitata dopo la migrazione. Per altri dettagli, vedere [Configurare Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Se in precedenza sono stati configurati Exchange criteri e regole della macchina virtuale, assicurarsi che siano efficaci.
- Acquisire familiarità con i cmdlet di PowerShell del servizio Cloud Voicemail per la modifica delle impostazioni utente.  

### <a name="user-experience-impact"></a>Impatto sull'esperienza utente

Di seguito è riportata una panoramica dell'esperienza di migrazione della segreteria telefonica dell'utente finale.


|Funzionalità  |Modifica dell'esperienza utente|
|---------|---------|
|Notifica tramite posta elettronica | Nessuna modifica<br>Nessun messaggio di posta elettronica viene inviato agli utenti per notificare l'attivazione/migrazione dell'account della segreteria telefonica. |
|Accesso ai messaggi precedenti | Nessuna modifica<br>Gli utenti hanno accesso ai messaggi vocali precedenti in tutti gli endpoint supportati. |
|Ricezione di VM in Outlook, App SFB| Nessuna modifica<br>Gli utenti continuano a ricevere i messaggi vocali in tutti gli endpoint supportati. |
|Trascrizione | Avanzata<br>La trascrizione della macchina virtuale ha una frequenza di accuratezza e linguaggi supportati molto più elevati rispetto a ExchUMO. |
|Impostazione utente | Nuova esperienza<br>Gli utenti possono modificare le proprie preferenze da un portale di impostazione utente (USP). Gli utenti possono accedere al proprio USP da un collegamento ipertestuale nel messaggio di posta elettronica della segreteria telefonica o dal pulsante User-Settings sul client SFB; https://aka.ms/vmsettings.
 |Funzionalità| Per informazioni dettagliate, vedere il confronto tra set di funzionalità. |
|regole di Outlook per i messaggi della macchina virtuale | Nessuna modifica<br>Le regole create in precedenza verranno applicate ai messaggi CVM dopo la migrazione.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestione e provisioning degli utenti in CVM

Verrà eseguito automaticamente il provisioning dei nuovi utenti Skype for Business per la segreteria telefonica cloud al momento della creazione. Per effettuare il provisioning di nuovi utenti della segreteria telefonica non è necessaria alcuna licenza o lavoro amministratore aggiuntivo. Vedere [Configurare Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail) per informazioni sulla gestione dei criteri per utenti nuovi e esistenti.

### <a name="admin-auto-attendant-management-experience"></a>Amministrazione'esperienza di gestione dell'operatore automatico

Per altre informazioni sugli operatori automatici, vedere [Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problemi noti

#### <a name="greeting-inconsistencies"></a>Incoerenze di saluto

L'accesso del Sottoscrittore potrebbe continuare a funzionare per il tenant fino a quando il servizio non viene completamente ritirato, anche dopo la migrazione di tutti gli utenti a Cloud Voicemail. Per evitare confusione dell'utente e un'esperienza incoerente, disabilitare l'accesso al Sottoscrittore dopo la modifica dei messaggi di saluto dopo la migrazione. A tale scopo, rimuovere il contatto EXUM per ogni riga di accesso del Sottoscrittore usando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Trasferimento della chiamata dell'operatore automatico a PSTN

Per trasferire una chiamata dell'operatore automatico a un numero di telefono PSTN esterno tramite Skype for Business Server o un servizio Response Group (RGS) in Skype for Business Server, creare un nuovo utente locale con inoltro di chiamata impostato sul numero di telefono PSTN o sul numero di telefono RGS. L'utente deve essere abilitato e configurato correttamente per VoIP aziendale e assegnare un criterio vocale.

#### <a name="shared-mailbox-is-still-accessible"></a>La cassetta postale condivisa è ancora accessibile

Una cassetta postale condivisa configurata con Exchange messaggistica unificata online continua a ricevere messaggi dopo la migrazione alla macchina virtuale ed essere accessibile agli utenti tramite Outlook. Tuttavia, l'accesso per modificare i messaggi di saluto di queste cassette postali non sarà disponibile dopo la migrazione alla CVM. I clienti con cassette postali condivise usate per acquisire i chiamanti dell'operatore automatico devono sfruttare le funzionalità di operatori automatici e cassette postali condivise delle code di chiamata una volta rilasciate (ETA ottobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Viene visualizzato il banner "Username is not using Skype for Business" (Il nome utente non usa Skype for Business)

Il servizio CVM è basato sull'infrastruttura di Microsoft Teams e le chiamate da un client Skype for Business potrebbero causare la visualizzazione di un banner informativo nel client che recita: "Username is not using Skype for Business. Per un'esperienza più completa, passare a Teams o avviare una riunione Skype.
Assicurarsi di aggiornare il client Skype for Business degli utenti all'aggiornamento client C2R più recente per impedire la visualizzazione di questo banner.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configura segreteria telefonica" consente di passare a OWA

Facendo clic su **Configura segreteria telefonica** dal client, i clienti Skype for Business Server 2015/2013 continueranno a passare alla pagina del portale di accesso Web (OWA) Office dopo la migrazione alla macchina virtuale. Tutte le impostazioni sono state rimosse dalla scheda Segreteria telefonica in OWA e verrà visualizzato un banner con un collegamento di reindirizzamento per consentire agli utenti di accedere al portale delle impostazioni utente della macchina virtuale.

#### <a name="changing-greeting-remotely"></a>Modifica del messaggio di saluto in remoto

L'accesso al sottoscrittore PSTN non è supportato in CVM. Per gli utenti che devono modificare il messaggio di saluto in remoto, è stata aggiunta un'opzione di menu "Cambia messaggio di saluto" al servizio IVR della segreteria telefonica per i client mobili. Gli utenti possono chiamare questo servizio premendo e tenendo premuto il tasto "1" sul dial pad del client mobile.