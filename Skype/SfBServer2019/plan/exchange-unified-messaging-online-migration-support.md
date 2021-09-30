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
description: Microsoft ritira il servizio Exchange messaggistica unificata online (ExchUMO) entro il 28 febbraio 2020. In questo articolo vengono riepilogate le informazioni che i clienti interessati devono conoscere e fare per pianificare la continuità aziendale.
ms.openlocfilehash: 1e6d24b05b8f1c6b8d2b47533edbd9ad79c5022e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013290"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Supporto per la migrazione della messaggistica unificata online di Exchange

> [!IMPORTANT]
> **Il servizio messaggistica unificata di Exchange Online è fuori supporto a partire dal 28 febbraio 2020, 17.00 ora pacifica. Tutti gli account di segreteria telefonica sono stati migrati al Cloud Voicemail da Microsoft. Il traffico rimanente dell'operatore automatico non verrà monitorato e potrebbe essere interrotto in qualsiasi momento.**

In riferimento [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) all'annuncio dell'8 febbraio 2019, Microsoft ritira il servizio Exchange Unified Messaging Online (ExchUMO) entro il 28 febbraio 2020. Questo articolo offre un riepilogo delle informazioni che i clienti interessati devono conoscere e fare per pianificare la continuità aziendale.

ExchUMO viene distribuito dai clienti per la segreteria telefonica, l'operatore automatico, la coda di chiamata e i servizi di integrazione fax. Microsoft prevede di aiutare i clienti a eseguire la migrazione a Sistema telefonico che supportano già migliaia di clienti in Skype for Business Online e Microsoft Teams.

La segreteria telefonica è principalmente una migrazione guidata da Microsoft; il coinvolgimento dell'amministratore e/o l'investimento potrebbe essere necessario per un sottoinsieme di clienti. L'operatore automatico è una migrazione guidata dall'amministratore. sarà necessario creare di nuovo gli alberi degli operatori automatici ExchUMO esistenti nel servizio cloud Operatore automatico cloud. I clienti che utilizzano una delle funzionalità exchUMO con un PBX di terze parti non verranno migrati nei servizi cloud di Skype perché non supportano sistemi PBX di terze parti. In questo [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)è stato annunciato un piano di ritiro per il supporto di terze parti e i clienti di questo modello di distribuzione possono eseguire la migrazione degli utenti a una delle piattaforme/servizi Di comunicazioni unificate di Microsoft o acquisire una soluzione di segreteria telefonica e/o operatore automatico di terze parti per tali utenti. L'integrazione fax non è supportata nei servizi basati su cloud. i clienti dovranno eseguire la migrazione a una soluzione di terze parti.

## <a name="who-is-affected"></a>Who è interessato?

I clienti che utilizzano una delle seguenti funzionalità del servizio Exchange messaggistica unificata online sono interessati:

- Servizio segreteria telefonica
- Operatore automatico servizio
- Servizio coda di chiamata
- Integrazione fax

> [!Note]
> I clienti che utilizzano una delle Exchange Server locale con la messaggistica unificata non sono interessati.

Altre informazioni sull'impatto dell'esperienza utente e dell'amministratore in [Impatto sull'esperienza utente](#user-experience-impact).

## <a name="migration-plan-overview"></a>Panoramica del piano di migrazione

Microsoft ha identificato diverse distribuzioni dei clienti che utilizzano le funzionalità di ExchUMO e che consentono ai clienti di eseguire la migrazione in base al piano seguente.

|Gruppo di clienti |Sequenza temporale  |Dettagli  |
|---------|---------|---------|
|Clienti pronti per la migrazione<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Messaggi vocali</ul>   |   Marzo - Maggio 2019  |Esempi:<ul><li>    Clienti con distribuzione e utilizzo della segreteria telefonica semplici<li>Clienti che hanno tutti i requisiti stabiliti per Microsoft per eseguire la migrazione<ul>|
|Clienti con prerequisiti<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Messaggi vocali<li>Operatore automatico<li>Coda chiamate</ul> |  Maggio - Dicembre 2019 |Esempi: <br><ul><li>Configurazione ibrida non completata<li>I numeri PSTN ibridi non sono impostati</ul>|
|Clienti che richiedono il coinvolgimento dell'amministratore & investimento del cliente<br><br>Funzionalità di cui eseguire la migrazione:<ul><li>segreteria telefonica<li>Operatore automatico<li>Code di chiamata<li>Integrazione fax</ul>| Entro febbraio 2020  | Esempi: <br><ul><li>Il servizio ExchUMO viene utilizzato da pbx di terze parti<li>Clienti con requisiti di accesso sottoscrittore PSTN<li>Clienti in SFB 2010 (non supportato)<li>Integrazione fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Linee guida per la migrazione della segreteria telefonica

### <a name="get-informed"></a>Informazioni

Acquisire familiarità con l'annuncio [di blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e questo articolo per pianificare una migrazione uniforme per gli utenti. Per [informazioni dettagliate sulle Sistema telefonico della segreteria telefonica,](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) vedere Check Skype for Business voicemail and options.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Stabilire una Skype for Business ibrida

Se non è stata stabilita una Skype for Business ibrida, è necessario farlo per consentire una migrazione uniforme degli utenti della segreteria telefonica. Per [ulteriori informazioni, vedere Configure Skype for Business hybrid.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)

> [!Note]
> Non è necessario eseguire la migrazione degli utenti online per la migrazione del servizio di segreteria telefonica. Tuttavia, per consentire agli utenti locali di sfruttare Sistema telefonico servizio di segreteria telefonica, è necessario stabilire una topologia ibrida.

### <a name="plan-your-auto-attendant-migration"></a>Pianificare la migrazione dell'operatore automatico

Gli amministratori possono iniziare a eseguire la migrazione degli operatori automatici da ExchUMO all'operatore automatico cloud in qualsiasi momento. Per [altri dettagli, vedi Configurare un operatore automatico](/microsoftteams/create-a-phone-system-auto-attendant) cloud.

Microsoft continua a offrire funzionalità aggiuntive dell'operatore automatico che i clienti potrebbero considerare necessarie per la migrazione. Gli amministratori devono valutare il set di funzionalità ed eseguire la migrazione delle istanze dell'operatore automatico di conseguenza. Per un confronto tra elenco di funzionalità, vedere matrice di funzionalità dei servizi basati su [cloud di ExchUMO e Azure.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Pianificare la convalida e il test post-migrazione della segreteria telefonica

La migrazione della segreteria telefonica è guidata da Microsoft. Gli amministratori non devono eseguire alcun'operazione, dato che è stata stabilita la topologia ibrida necessaria. Microsoft esegue la convalida e il test necessari per assicurarsi che la migrazione della segreteria telefonica degli utenti non sia interrotta. Gli amministratori sono invitati a eseguire test e convalida sul loro lato. Per [un piano di test consigliato, vedere Piano di test consigliato e Convalida post-migrazione](#suggested-test-plan-and-post-migration-validation-for-admins) per gli amministratori.

> [!Note]
> Lync Server 2010 non è supportato. Se si è in una distribuzione di server 2010, è consigliabile pianificare un aggiornamento del server o prendere in considerazione la migrazione degli utenti a Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorare l'interfaccia di notifica di amministrazione

Guarda un avviso nell'interfaccia di notifica dell'amministratore con ulteriori dettagli e una sequenza temporale sulla migrazione degli utenti. Le notifiche vengono inviate almeno 30 giorni prima del periodo di migrazione.

> [!Note]
> Se si riceve una notifica con la sequenza temporale di migrazione degli utenti e si desidera posticipare la migrazione per un motivo critico per l'azienda, è possibile farlo contattando il Supporto Tecnico Microsoft. Non è possibile posticipare la migrazione oltre la data di ritiro del 28 febbraio 2020. Per i clienti che potrebbero avere altre domande, contattare il team dell'account o il supporto Tecnico Microsoft. I clienti che usano Microsoft 365 o Office 365 possono inviare un caso di supporto tramite il interfaccia di amministrazione di Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Prendere in considerazione la possibilità di acconsentire esplicitamente a una migrazione pianificata

È possibile acconsentire esplicitamente a una migrazione pianificata del servizio segreteria telefonica a CVM. Prima di acconsentire esplicitamente, leggere i dettagli di questo articolo, in particolare le sezioni seguenti:

- Passaggi di migrazione (questa sezione)
- Matrice di funzionalità dei servizi basati su cloud di ExchUMO e Azure
- Impatto sull'esperienza utente

Quando si sceglie una migrazione gestita, non si riceverà una notifica pre-migrazione di 30 giorni nel centro messaggi Microsoft 365 portale di amministrazione.

Per acconsentire esplicitamente a una migrazione pianificata, inviare una richiesta di posta elettronica dall'indirizzo di posta elettronica dell'amministratore [cvm@microsoft.com](mailto:cvm@microsoft.com) con le informazioni seguenti:

- Data preferita (martedì): le ondate di migrazione vengono eseguite ogni martedì. Selezionare una data di martedì non successiva al 3/12/2019.
 
- ID tenant: numero di 32 caratteri in questo formato 0046728c-688a-4472-a38f-098fec60ac6x. È possibile trovare l'ID tenant nel portale Microsoft 365 di amministrazione di Azure AD o usando il cmdlet PowerShell seguente:`Get-CsTenant | Select ObjectId`

Una volta completata la migrazione del tenant, si riceverà una conferma tramite posta elettronica.

## <a name="auto-attendant-migration-guidelines"></a>Linee guida per la migrazione dell'operatore automatico

gli amministratori dell'organizzazione di Microsoft 365 e Office 365 devono creare di nuovo gli operatori automatici di messaggistica unificata di Exchange Um Online nel servizio Microsoft Cloud Operatore automatico e passare loro i numeri di telefono locali prima della data di ritiro del servizio UMO di Exchange del 28 febbraio 2020. Questa è la linea guida consigliata per eseguire correttamente la migrazione e testare i nuovi operatori automatici cloud. Se si dispone di un numero elevato di operatori automatici, è possibile utilizzare il Operatore automatico di messaggistica unificata di Exchange per gli script di migrazione di [Cloud Operatore automatico](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) per semplificare la migrazione in blocco degli operatori automatici.

### <a name="auto-attendant-setup"></a>Configurazione dell’operatore automatico

Consigliamo vivamente di avviare la configurazione dei nuovi operatori automatici in anticipo per evitare problemi dell'ultimo minuto e acquisire familiarità con le funzionalità e l'esperienza del servizio Cloud Operatore automatico. Per gli operatori automatici che richiedono una o più funzionalità gap, è possibile creare e testare gli operatori automatici quando le funzionalità gap sono disponibili per prepararsi alla distribuzione. Per ulteriori informazioni sulle funzionalità gap, vedere [l'Appendice](#appendix).

1. Utilizzare i Exchange umo per esportare la configurazione degli operatori automatici esistenti utilizzando [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Utilizzare il cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell per esportare i file multimediali dei messaggi di saluto (se utilizzati) e convertirli in .mp3 formato.

3. Seguire le istruzioni in [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e Set up a Cloud auto attendant to create auto [attendants](/microsoftteams/create-a-phone-system-auto-attendant) by using the Microsoft Teams admin center or PowerShell.

4. Rivedere i messaggi di saluto se le opzioni di menu sono cambiate.

5. Configurare i trasferimenti ai Response Group utilizzando la soluzione alternativa "Trasferimento Operatore automatico chiamata a PSTN" nella [sezione Problemi](#known-issues) noti di questo articolo.  

6. Testare i nuovi operatori automatici chiamandoli internamente o assegnando un numero di telefono di prova.  

### <a name="cutover"></a>Completa

1. Passare dai numeri di telefono Exchange operatori automatici UMO ai nuovi operatori automatici.
2. Spostare l'URI SIP dall'oggetto contatto all'account della risorsa.
3. Testare e convalidare gli operatori automatici utilizzando i nuovi numeri di telefono assegnati.

## <a name="appendix"></a>Appendice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice di funzionalità dei servizi basati su cloud di ExchUMO e Azure

| Servizio | Livello funzionalità | Funzionalità | Note  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Funzionalità del servizio| Supporto PBX di terze parti    | Inclusione di tutte le funzionalità fornite a PBX di terze parti, ad esempio LWI (Message Waiting Indicator) tramite i messaggi di notifica SIP Exchange messaggistica unificata online | N   | Y    |
| VM | Funzionalità del servizio  | Supporto Skype for Business Server   |  | Y | Y    |
| VM | Funzionalità del servizio | Supporto Microsoft Teams|  | Y | N    |
| VM | Funzionalità del servizio | eDiscovery e blocco  | Per sicurezza e conformità  | Y | Y    |
| VM | Funzionalità del servizio | Exchange Supporto delle regole | Per sicurezza e conformità  | Y | Y    |
| VM | Funzionalità utente | Accesso con accesso remoto PSTN  | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Delegato  | e-mail chiamata senza chiamata  | N | Y    |
| VM | Funzionalità utente | PstN Outlook Voice Access   | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Accesso esterno con un endpoint autenticato | Chiamata del servizio di segreteria telefonica per ascoltare i messaggi vocali e modificare le impostazioni della segreteria telefonica| Y | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la segreteria telefonica   |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare il messaggio di saluto personale  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per creare un messaggio di saluto fuori sede  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare la lingua predefinita  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per sovrascrivere il messaggio di saluto predefinito con TTS  |  | Y | N    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (dispositivo autenticato) |  | Y | Y    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (PSTN) - riprodurre al telefono |  | N | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la trascrizione |  | N | Y    |
| VM | Funzionalità utente | Trascrizione  |  | Y | Y    |
| VM | Funzionalità utente | MWI (Message Waiting Indicator) con messaggi di notifica SIP |  | N | Y    |
| VM | Funzionalità utente | Formato di file audio MP3 in Outlook    |  | Y | Y    |
| VM | Funzionalità utente | Controllo della riproduzione a velocità variabile |  | Y | Y    |
| VM | Funzionalità utente | Inoltrare una segreteria telefonica  | Inoltrare una segreteria telefonica ricevuta ad altri utenti | Y | Y    |
| VM | Funzionalità utente | Invio di un messaggio vocale a un gruppo di utenti  |Trasmissione della segreteria telefonica   | N | Y   |
| VM | Funzionalità utente | Notifica della segreteria telefonica tramite SMS    | Gli utenti possono ricevere un SMS quando hanno una nuova segreteria telefonica    | N | Y    |
| VM | Funzionalità utente | Lingue di saluto supportate | Dettagli qui: [Cosa sono gli operatori automatici cloud?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | Funzionalità utente | Regole di ricezione chiamata |  | Y | Y    |
| VM | Funzionalità utente | Riproduci al telefono (PSTN) - Per riprodurre il messaggio | Chiamami nella mia cella per ascoltare il messaggio vocale  | N | Y    |
| VM | Funzionalità utente | Riproduci al telefono (Auth)- per riprodurre il messaggio | Chiamami sul dispositivo autenticato  | N | Y    |
| VM | Funzionalità utente | Cassetta postale condivisa tra più utenti |  | Y | Y    |
| VM | Funzionalità chiamante  | Esperienza chiamante - segreteria telefonica protetta | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come protetto| N | Y    |
| VM | Funzionalità chiamante  | Esperienza chiamante - segreteria telefonica privata | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come privato  | N | Y    |
| VM | Funzionalità chiamante  | Rilevamento del silenzio   |  | N | Y    |
| VM | Tenant-Admin funzionalità | Segreteria telefonica protetta a livello di server    | L'amministratore tenant può configurare una regola a livello di servizio per contrassegnare la segreteria telefonica in arrivo come protetta | Y | Y    |
| VM | Tenant-Admin funzionalità | Modificare il limite di tempo della durata della registrazione  |     | Y | Y    |
| VM | Tenant-Admin funzionalità | Modificare il timeout di rilevamento del silenzio    |  | N/D    | Y    |
| VM | Tenant-Admin funzionalità | Modificare il numero di errori di input | CVM: hard coded to 3 | N | Y    |
| VM | Tenant-Admin funzionalità | Modificare la lingua predefinita |  | Y | Y    |
| VM | Tenant-Admin funzionalità | Disabilitare/abilitare la trascrizione |  | Y | Y    |
| VM | Tenant-Admin funzionalità | Disabilitare/abilitare la notifica di chiamata senza chiamata senza chiamata |  | N | Y    |
| VM | Tenant-Admin funzionalità | Consenti a Microsoft di migliorare l'anteprima della casella vocale    |  | Y | Y    |
| VM | Tenant-Admin funzionalità | Personalizzare l'SMS per gli utenti abilitati|  | N/D    | Y    |
| VM | Tenant-Admin funzionalità | Mascheramento volgare trascrizione|  | Y | N    |
| VM | Tenant-Admin funzionalità | Criteri segreteria telefonica    |   | Y | Y    |
| VM | Tenant-Admin funzionalità | Amministrazione portale Web   |  | CY19   | Y    |
| VM | Tenant-Admin funzionalità | PowerShell   |  | Y | Y    |
| Messaggistica unificata | Funzionalità utente | Indicatore di messaggi in attesa (MWI) Skype for Business telefoni certificati   |Può essere fornito dal partner telefonico  | No | Sì    |
| AA | Funzionalità del servizio | AA support 3rd-party PBX    |  | N | Y    |
| AA | Funzionalità del servizio | Supporto Skype for Business Server   |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto Microsoft Teams|  | Y | N    |
| AA | Funzionalità del servizio | Composizione per nome, input DTMF    |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione per nome, input vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto multilingue | Informazioni dettagliate sulla lingua: [Che cos'è l'operatore automatico cloud?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento all'operatore, al CQ o a un utente |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN internamente (DID RNL)  |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferire il numero PSTN esternamente  |  | Vedere la sezione Problemi noti riportata di seguito | Y    |
| AA | Funzionalità del servizio | Ore lavorative |  | Y | Y    |
| AA | Funzionalità del servizio | Opzioni di menu | Opzioni del menu IVR  | Y | Y    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN cloud ad AA |  | Y | N    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN locale ad AA  |  | Y | Y    |
| AA | Funzionalità del servizio | Selezione utente personalizzata  | Consentire ai chiamanti di raggiungere un elenco personalizzato di utenti dell'organizzazione| Y | Y    |
| AA | Funzionalità del servizio | Trattamento dopo le ore e le festività  |  | Y | Y    |
| AA | Funzionalità del servizio | Messaggio di saluto personalizzato con sintesi vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione del numero di interno   | Raggiungere un utente componendo il proprio interno  | Y   | Y    |
| AA | Funzionalità del servizio | Cassetta postale per i chiamanti AA per lasciare un messaggio    |  | Y   | Y    |
| AA | Funzionalità del servizio | Assegnazioni di più numeri PSTN a un AA|  | Y | Y    |
| AA | Tenant-Admin funzionalità | Amministrazione portale Web   |  | Y | N    |
| AA | Tenant-Admin funzionalità | Cmdlet di PowerShell  |  | Y | Y    |
| Fax| Funzionalità del servizio | Integrazione fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Piano di test consigliato e convalida post-migrazione per gli amministratori

Per verificare che gli utenti siano stati migrati in Cloud Voicemail, lasciare una segreteria telefonica a un utente e controllare il corpo del messaggio in Outlook. Cloud Voicemail i messaggi hanno un piè di pagina che legge:

"Grazie per l'uso della trascrizione! Se non vedi una trascrizione sopra, è perché la qualità audio non era abbastanza chiara da trascrivere."

Quando si testa la funzionalità di segreteria telefonica dopo la migrazione degli utenti, considerare gli scenari seguenti:

- Convalidare l'accesso alla segreteria telefonica in tutti i tipi di endpoint dell'organizzazione, ad esempio app e telefoni IP.
- Verificare con gli utenti di esempio che i messaggi di saluto personalizzati configurati siano riprodotti ai chiamanti.
- Se l'organizzazione ha un requisito legale o di conformità per disabilitare la trascrizione per gli utenti, assicurarsi che sia disabilitata dopo la migrazione. Per ulteriori dettagli, vedere [Set up Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Se in precedenza sono stati configurati Exchange criteri e regole della macchina virtuale, assicurarsi che siano efficaci.
- Acquisire familiarità con i cmdlet di PowerShell Cloud Voicemail servizio per la modifica delle impostazioni utente.  

### <a name="user-experience-impact"></a>Impatto sull'esperienza utente

Di seguito è riportata una panoramica dell'esperienza di migrazione della segreteria telefonica dell'utente finale.


|Funzionalità  |Modifica dell'esperienza utente|
|---------|---------|
|Notifica tramite posta elettronica | Nessuna modifica<br>Non viene inviato alcun messaggio di posta elettronica agli utenti che comunicano loro l'attivazione/migrazione dell'account della segreteria telefonica. |
|Accesso ai messaggi precedenti | Nessuna modifica<br>Gli utenti hanno accesso ai messaggi vocali precedenti in tutti gli endpoint supportati. |
|Ricezione di macchine virtuali in outlook, app SFB| Nessuna modifica<br>Gli utenti continuano a ricevere i messaggi della segreteria telefonica in tutti gli endpoint supportati. |
|Trascrizione | Enhanced<br>La trascrizione CVM ha una frequenza di accuratezza molto più elevata e lingue supportate rispetto a ExchUMO. |
|Impostazione utente | Nuova esperienza<br>Gli utenti possono modificare le proprie preferenze da un portale delle impostazioni utente (USP). Gli utenti possono accedere al proprio USP da un collegamento ipertestuale nella posta elettronica della segreteria telefonica o dal pulsante User-Settings sul client SFB. https://aka.ms/vmsettings.
 |Funzionalità| Per informazioni dettagliate, vedere il confronto tra set di funzionalità. |
|Outlook regole per i messaggi della macchina virtuale | Nessuna modifica<br>Le regole create in precedenza verranno applicate ai messaggi CVM dopo la migrazione.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestione e provisioning degli utenti in CVM

Quando vengono Skype for Business nuovi utenti, verrà eseguito automaticamente il provisioning della segreteria telefonica cloud. Per eseguire il provisioning di nuovi utenti di segreteria telefonica non è necessaria alcuna licenza o lavoro amministrativo aggiuntivo. Vedi [Configurare Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail) per informazioni sulla gestione dei criteri per gli utenti esistenti e nuovi.

### <a name="admin-auto-attendant-management-experience"></a>Esperienza di Operatore automatico amministratore

Per ulteriori informazioni sugli operatori automatici, vedere [Set up a Cloud auto attendant.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Problemi noti

#### <a name="greeting-inconsistencies"></a>Incoerenze di saluto

L'accesso del sottoscrittore potrebbe continuare a funzionare per il tenant fino a quando il servizio non viene completamente ritirato, anche dopo che tutti gli utenti sono stati migrati a Cloud Voicemail. Per evitare confusione dell'utente e un'esperienza incoerente, disabilitare l'accesso del sottoscrittore poiché i messaggi di saluto cambiano dopo la migrazione. A tale scopo, rimuovere il contatto exUM per ogni linea di accesso sottoscrittore utilizzando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Operatore automatico trasferimento di chiamata a PSTN

Per trasferire una chiamata dell'operatore automatico a un numero di telefono PSTN esterno tramite Skype for Business Server o un servizio RGS (Response Group) in Skype for Business Server, creare un nuovo utente locale con l'inoltro di chiamata impostato sul numero di telefono PSTN o sul numero di telefono RGS. L'utente deve essere abilitato e configurato correttamente per VoIP aziendale e disporre di un criterio vocale assegnato.

#### <a name="shared-mailbox-is-still-accessible"></a>La cassetta postale condivisa è ancora accessibile

Una cassetta postale condivisa configurata Exchange messaggistica unificata online continua a ricevere messaggi dopo la migrazione a CVM ed essere accessibile agli utenti tramite Outlook. Tuttavia, l'accesso per modificare i messaggi di saluto di queste cassette postali non sarà disponibile dopo la migrazione a CVM. I clienti con cassette postali condivise che vengono utilizzate per acquisire i chiamanti degli operatori automatici devono sfruttare le funzionalità Diario automatico e Code di chiamata Cassette postali condivise una volta rilasciate (ETA ottobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Visualizzazione banner "Nome utente non Skype for Business"

Il servizio CVM si basa sull'infrastruttura Microsoft Teams e le chiamate da un client Skype for Business potrebbero causare la visualizzazione di un banner di informazioni sul client con la seguente informazione: "Il nome utente non utilizza Skype for Business. Per un'esperienza più ricca, passa a Teams o avvia una Skype riunione."
Assicurati di aggiornare il client Skype for Business degli utenti all'aggiornamento client C2R più recente per impedire la visualizzazione di questo banner.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurare la segreteria telefonica" consente di OWA

Se  si fa clic su Configura casella vocale dal client, i clienti Skype for Business Server 2015/2013 continueranno Skype for Business Server passare alla pagina del portale di Office Web Access (OWA) dopo la migrazione a CVM. Tutte le impostazioni sono state rimosse dalla scheda Segreteria telefonica in OWA e verrà visualizzato un banner con un collegamento di reindirizzamento per consentire agli utenti di accedere al portale delle impostazioni utente CVM.

#### <a name="changing-greeting-remotely"></a>Modifica del messaggio di saluto in remoto

L'accesso del sottoscrittore PSTN non è supportato in CVM. Per gli utenti che devono modificare il messaggio di saluto in remoto, è stata aggiunta un'opzione di menu "Cambia messaggio di saluto" al servizio IVR della segreteria telefonica per i client mobili. Gli utenti possono chiamare questo servizio premendo e tenendo premuto il tasto "1" sulla tastiera del client mobile.