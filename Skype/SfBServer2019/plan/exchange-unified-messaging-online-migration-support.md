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
localization_priority: Normal
description: Microsoft sta ritirando il servizio di messaggistica unificata di Exchange Online (ExchUMO) entro il 28 febbraio 2020. In questo articolo vengono riepilogati i clienti coinvolti che devono conoscere e fare per pianificare la continuità aziendale.
ms.openlocfilehash: 5d7d9b2e488c61c881395ad00d2675d749e5e30f
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359302"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Supporto per la migrazione della messaggistica unificata online di Exchange

> [!IMPORTANT]
> **Il servizio messaggistica unificata in Exchange Online non è supportato al momento del 28 febbraio 2020 Pacifico. Tutti gli account della segreteria telefonica sono stati migrati al servizio cloud voicemail da Microsoft. Qualsiasi traffico operatore automatico rimanente non verrà monitorato e potrebbe essere interrotto in qualsiasi momento.**

In riferimento all' [annuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) dell'8 febbraio 2019, Microsoft sta ritirando il servizio di messaggistica unificata di Exchange Online (ExchUMO) entro il 28 febbraio 2020. In questo articolo viene offerta una sintesi dei requisiti che i clienti coinvolti devono conoscere e fare per pianificare la continuità aziendale.

ExchUMO è distribuito dai clienti per la segreteria telefonica, l'operatore automatico, la coda di chiamata e i servizi di integrazione fax. Microsoft intende consentire ai clienti di eseguire la migrazione a servizi di sistema telefonico che supportano già migliaia di clienti su Skype for business online e Microsoft teams.

La segreteria telefonica è principalmente una migrazione basata su Microsoft. per un sottoinsieme di clienti, potrebbe essere necessario un coinvolgimento e/o un investimento di amministratore. Operatore automatico è una migrazione guidata dall'amministratore; sarà necessario ricreare gli alberi degli operatori automatici di ExchUMO esistenti nel servizio cloud per l'operatore automatico cloud. I clienti che utilizzano una qualsiasi delle funzionalità di ExchUMO con un sistema PBX di terze parti non verranno migrati ai servizi cloud di Skype perché non supportano sistemi PBX di terze parti. Un piano pensionistico per il supporto di terze parti è stato annunciato in [questo Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)e i clienti di questo modello di distribuzione possono eseguire la migrazione degli utenti a una delle piattaforme/servizi Microsoft Unified Communications o acquisire una segreteria telefonica di terze parti e/o una soluzione operatore automatico per questi utenti. L'integrazione dei fax non è supportata nei servizi basati sul cloud. i clienti dovranno eseguire la migrazione a una soluzione di terze parti.

## <a name="who-is-affected"></a>Chi è influenzato?

I clienti che utilizzano una delle caratteristiche seguenti del servizio messaggistica unificata di Exchange sono coinvolti:

- Servizio segreteria telefonica
- Servizio operatore automatico
- Servizio code di chiamata
- Integrazione fax

> [!Note]
> I clienti che utilizzano uno qualsiasi dei server Exchange locali con la messaggistica unificata non sono intaccati.

Per ulteriori informazioni, vedere l'utente e l'impatto sull'esperienza di amministratore nell' [impatto sull'esperienza utente](#user-experience-impact).

## <a name="migration-plan-overview"></a>Panoramica del piano di migrazione

Microsoft ha individuato diverse distribuzioni dei clienti che utilizzano funzionalità di ExchUMO e aiuteranno i clienti a eseguire la migrazione in base al piano seguente.

|Gruppo clienti |Sequenza temporale  |Dettagli  |
|---------|---------|---------|
|Clienti pronti per la migrazione<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Segreteria telefonica</ul>   |   Marzo-maggio 2019  |Esempi:<ul><li>    Clienti con semplicità di distribuzione e utilizzo della segreteria telefonica<li>Clienti con tutti i requisiti stabiliti per Microsoft per eseguire la migrazione<ul>|
|Clienti con prerequisiti<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Segreteria telefonica<li>Operatore automatico<li>Coda di chiamata</ul> |  Maggio — dicembre 2019 |Esempi: <br><ul><li>La configurazione ibrida non è completa<li>I numeri PSTN ibridi non sono configurati</ul>|
|Clienti che richiedono coinvolgimento dell'amministratore & investimento del cliente<br><br>Funzionalità di cui eseguire la migrazione:<ul><li>Voicemail<li>Operatore automatico<li>Code di chiamata<li>Integrazione fax</ul>| Entro febbraio 2020  | Esempi: <br><ul><li>Il servizio ExchUMO è utilizzato da PBX di terze parti<li>Clienti con requisiti di accesso del sottoscrittore PSTN<li>Clienti su questo 2010 (non supportato)<li>Integrazione fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Linee guida sulla migrazione della segreteria telefonica

### <a name="get-informed"></a>Ottenere informazioni

Familiarizzare con l' [annuncio di Blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e questo articolo per pianificare una migrazione agevole per gli utenti. Vedere [verificare la segreteria telefonica di Skype for business e le opzioni](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) per informazioni dettagliate sulle funzionalità di segreteria telefonica del sistema telefonico.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Creare una topologia ibrida di Skype for business

Se non si dispone di una topologia ibrida di Skype for business stabilita, è necessario farlo per abilitare una migrazione agevole degli utenti della segreteria telefonica. Per ulteriori informazioni, vedere [Configurare Skype for business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) .

> [!Note]
> Non è necessario eseguire la migrazione degli utenti online per la migrazione del servizio segreteria telefonica. Tuttavia, per gli utenti locali per sfruttare il servizio segreteria telefonica del sistema telefonico, è necessario stabilire una topologia ibrida.

### <a name="plan-your-auto-attendant-migration"></a>Pianificare la migrazione dell'operatore automatico

Gli amministratori possono avviare la migrazione degli operatori automatici da ExchUMO all'operatore automatico cloud in qualsiasi momento. Per ulteriori informazioni, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft continua a fornire ulteriori funzionalità di operatore automatico che i clienti potrebbero prendere in considerazione per la migrazione. Gli amministratori devono valutare il set di caratteristiche e migrare le istanze dell'operatore automatico di conseguenza. Per un confronto tra gli elenchi di funzionalità, vedere la [matrice di caratteristiche dei servizi basati su cloud di ExchUMO e Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Pianificare la convalida e il testing di post-migrazione della segreteria telefonica

La migrazione della segreteria telefonica è basata su Microsoft. Gli amministratori non sono tenuti a eseguire alcuna operazione, a condizione che sia stata stabilita la topologia ibrida prerequisita. Microsoft esegue la convalida e il testing necessari per assicurarsi che la migrazione della segreteria telefonica degli utenti non venga interrotta. Gli amministratori sono invitati a eseguire il testing e la convalida dalla propria parte. Vedere il [piano di testing suggerito e la convalida dopo la migrazione per gli amministratori](#suggested-test-plan-and-post-migration-validation-for-admins) per un piano di testing consigliato.

> [!Note]
> Lync Server 2010 non è supportato. Se si è in una distribuzione di 2010 Server, è consigliabile pianificare l'aggiornamento di un server o valutare la possibilità di migrare gli utenti a Microsoft teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorare il centro notifiche di amministrazione

Guardare un avviso nel centro notifiche di amministrazione con ulteriori dettagli e una sequenza temporale relativa alla migrazione degli utenti. Le notifiche vengono inviate almeno 30 giorni prima del periodo di migrazione.

> [!Note]
> Se è stata ricevuta una notifica con la sequenza temporale della migrazione degli utenti e si desidera posticipare la migrazione per motivi aziendali, è possibile contattare il supporto tecnico Microsoft. Non è possibile posticipare la migrazione oltre la data di pensionamento del 28 febbraio 2020. Per i clienti che potrebbero avere altre domande, contattare il team account o il supporto tecnico Microsoft. I clienti che già utilizzano Microsoft 365 o Office 365 possono inviare un caso di supporto tramite l'interfaccia di amministrazione di Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considerare la possibilità di optare per una migrazione pianificata

È possibile optare per una migrazione del servizio di segreteria telefonica pianificata a CVM. Prima di procedere con la scelta, esaminare i dettagli di questo articolo, in particolare le sezioni seguenti:

- Passaggi di migrazione (questa sezione)
- Matrice delle funzionalità dei servizi basati su cloud di ExchUMO e Azure
- Impatto sull'esperienza utente

Quando si sceglie una migrazione gestita, non si riceverà una notifica di 30 giorni prima della migrazione nel centro messaggi del portale di amministrazione di Microsoft 365.

Per optare per una migrazione pianificata, inviare una richiesta di posta elettronica dall'indirizzo di posta elettronica dell'amministratore a [CVM@microsoft.com](mailto:cvm@microsoft.com) con le seguenti informazioni:

- Data preferita (martedì): le ondate di migrazione vengono eseguite ogni martedì. Selezionare una data di martedì che non superi i 12/3/2019.
 
- ID tenant: 32 caratteri numerici in questo formato 0046728c-688a-4472-a38f-098fec60ac6x. È possibile trovare l'ID tenant nel portale di amministrazione di Microsoft 365 in Azure AD o utilizzando il cmdlet di PowerShell seguente: `Get-CsTenant | Select ObjectId`

Una volta che il tenant ha eseguito la migrazione, si riceverà una conferma tramite posta elettronica.

## <a name="auto-attendant-migration-guidelines"></a>Linee guida per la migrazione degli operatori automatici

Gli amministratori dell'organizzazione di Microsoft 365 e Office 365 sono tenuti a ricreare gli operatori automatici di messaggistica unificata di Exchange nel servizio Microsoft Cloud Auto Attendant e a commutare i loro numeri di telefono locali prima della data di pensionamento del servizio Exchange UMO del 28 febbraio 2020. Questa è la linea guida consigliata per eseguire correttamente la migrazione e testare nuovi operatori automatici cloud. Se si dispone di un numero elevato di operatori automatici, è possibile utilizzare l' [operatore automatico di messaggistica unificata di Exchange per gli script di migrazione degli operatori](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automatici del cloud per semplificare la migrazione in blocco degli operatori automatici.

### <a name="auto-attendant-setup"></a>Installazione dell'operatore automatico

È consigliabile avviare la configurazione dei nuovi operatori automatici per evitare problemi relativi all'ultimo minuto e acquisire familiarità con la funzionalità e l'esperienza del servizio operatore automatico cloud. Per gli operatori automatici che richiedono una o più funzionalità di Gap, è possibile creare e testare gli operatori automatici quando le funzionalità Gap sono disponibili per prepararsi per la distribuzione. Per ulteriori informazioni sulle funzionalità Gap, vedere l' [appendice](#appendix).

1. Utilizzare i cmdlet di UMO di Exchange per esportare la configurazione degli operatori automatici esistenti utilizzando [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Utilizzare il cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell per esportare i file multimediali di saluto (se usati) e convertirli in formato. mp3.
3. Seguire le istruzioni riportate in [Plan cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) per creare operatori automatici utilizzando l'interfaccia di amministrazione di Microsoft teams o PowerShell.
4. Esaminare i messaggi di saluto se le opzioni di menu sono state modificate.
5. Configurare i trasferimenti ai Response Group utilizzando la soluzione "trasferimento automatico chiamata al servizio PSTN" nella sezione [problemi noti](#known-issues) di questo articolo.  
6. Testare i nuovi operatori automatici chiamandoli internamente o assegnando un numero di telefono di prova.  

### <a name="cutover"></a>Completa

1. Passare i numeri di telefono dagli operatori automatici di Exchange UMO ai nuovi operatori automatici.
2. Spostare l'URI SIP dall'oggetto contatto nell'account della risorsa.
3. Testare e convalidare gli operatori automatici utilizzando i numeri di telefono appena assegnati.

## <a name="appendix"></a>Appendice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice delle funzionalità dei servizi basati su cloud di ExchUMO e Azure

| Servizio | Livello di funzionalità | Funzionalità | Note  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Funzionalità del servizio| Supporto del sistema PBX di terze parti    | Inclusione di tutte le funzionalità fornite a PBX di terze parti, ad esempio MWI (indicatore di messaggio in attesa) tramite messaggi SIP NOTIFY dalla messaggistica unificata di Exchange Online | N   | Y    |
| VM | Funzionalità del servizio  | Supporto di Skype for Business Server   |  | Y | Y    |
| VM | Funzionalità del servizio | Supporto di Microsoft Teams|  | Y | N    |
| VM | Funzionalità del servizio | eDiscovery e blocco  | Per la sicurezza e la conformità  | Y | Y    |
| VM | Funzionalità del servizio | Supporto delle regole di Exchange | Per la sicurezza e la conformità  | Y | Y    |
| VM | Funzionalità utente | Accesso esterno PSTN  | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Delegato  | email di chiamata senza risposta  | N | Y    |
| VM | Funzionalità utente | PSTN Outlook Voice Access   | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Accesso esterno tramite un endpoint autenticato | Chiamata del servizio segreteria telefonica per l'ascolto dei messaggi vocali e la modifica delle impostazioni della segreteria telefonica| Y | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la segreteria telefonica   |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare il messaggio di saluto personale  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per creare un messaggio di saluto fuori sede  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare la lingua predefinita  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per sovrascrivere il messaggio di saluto predefinito con TTS  |  | Y | N    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (dispositivo autenticato) |  | Y | Y    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (PSTN): Ascolta al telefono |  | N | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la trascrizione |  | N | Y    |
| VM | Funzionalità utente | Trascrizione  |  | Y | Y    |
| VM | Funzionalità utente | MWI (indicatore di messaggio in attesa) tramite messaggi SIP NOTIFY |  | N | Y    |
| VM | Funzionalità utente | Formato di file audio MP3 in Outlook    |  | Y | Y    |
| VM | Funzionalità utente | Controllo velocità di riproduzione variabile |  | Y | Y    |
| VM | Funzionalità utente | Inoltrare una segreteria telefonica  | Inoltrare una segreteria telefonica ricevuta ad altri utenti | Y | Y    |
| VM | Funzionalità utente | Invio di un messaggio vocale a un gruppo di utenti  |Trasmissione della segreteria telefonica   | N | Y   |
| VM | Funzionalità utente | Notifica della segreteria telefonica tramite SMS    | Gli utenti possono ricevere un SMS quando hanno una nuova segreteria telefonica    | N | Y    |
| VM | Funzionalità utente | Lingue di saluto supportate | Informazioni dettagliate: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | Funzionalità utente | Regole di ricezione chiamata |  | Y | Y    |
| VM | Funzionalità utente | Ascolta al telefono (PSTN)-per riprodurre il messaggio | Chiamami sul mio cellulare per ascoltare il messaggio vocale  | N | Y    |
| VM | Funzionalità utente | Ascolta al telefono (auth)-per riprodurre il messaggio | Chiamami sul dispositivo autenticato  | Y | Y    |
| VM | Funzionalità utente | Cassetta postale condivisa tra più utenti |  | Y | Y    |
| VM | Funzionalità del chiamante  | Esperienza chiamante: protezione della segreteria telefonica | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come protetto| N | Y    |
| VM | Funzionalità del chiamante  | Esperienza chiamante-segreteria telefonica privata | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come privato  | N | Y    |
| VM | Funzionalità del chiamante  | Rilevamento del silenzio   |  | N | Y    |
| VM | Funzionalità tenant-admin | Segreteria telefonica protetta a livello di server    | Tenant-admin può configurare una regola a livello di servizio per contrassegnare la segreteria telefonica in arrivo come protetta | Y | Y    |
| VM | Funzionalità tenant-admin | Modificare la durata del periodo di registrazione  |     | Y | Y    |
| VM | Funzionalità tenant-admin | Modificare il timeout di rilevamento del silenzio    |  | N/D    | Y    |
| VM | Funzionalità tenant-admin | Modificare il numero di errori di input | CVM: hardcoded su 3 | N | Y    |
| VM | Funzionalità tenant-admin | Modificare la lingua predefinita |  | Y | Y    |
| VM | Funzionalità tenant-admin | Disabilitazione/abilitazione della trascrizione |  | Y | Y    |
| VM | Funzionalità tenant-admin | Disabilitare/attivare la notifica di chiamata senza risposta |  | N | Y    |
| VM | Funzionalità tenant-admin | Consenti a Microsoft di migliorare l'anteprima della casella vocale    |  | Y | Y    |
| VM | Funzionalità tenant-admin | Personalizzazione del messaggio di testo per gli utenti abilitati|  | N/D    | Y    |
| VM | Funzionalità tenant-admin | Trascrizione mascheramento parolacce|  | Y | N    |
| VM | Funzionalità tenant-admin | Criteri di segreteria telefonica    |   | Y | Y    |
| VM | Funzionalità tenant-admin | Amministrazione portale Web   |  | CY19   | Y    |
| VM | Funzionalità tenant-admin | PowerShell   |  | Y | Y    |
| MESSAGGISTICA unificata | Funzionalità utente | Indicatore di messaggi in attesa (MWI) su telefoni certificati Skype for business   |Può essere fornito dal partner telefonico  | No | Sì    |
| AA | Funzionalità del servizio | Supporto di terze parti PBX di AA    |  | N | Y    |
| AA | Funzionalità del servizio | Supporto di Skype for Business Server   |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto di Microsoft Teams|  | Y | N    |
| AA | Funzionalità del servizio | Composizione per nome, input DTMF    |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione per nome, input vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto multilingue | Informazioni dettagliate sulla lingua: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento all'operatore, al CQ o a un utente |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN internamente (DID inversa)  |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN esternamente  |  | Vedere la sezione problemi noti riportati di seguito | Y    |
| AA | Funzionalità del servizio | Ore lavorative |  | Y | Y    |
| AA | Funzionalità del servizio | Opzioni di menu | Opzioni di menu IVR  | Y | Y    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN cloud a AA |  | Y | N    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN su AA  |  | Y | Y    |
| AA | Funzionalità del servizio | Selezione personalizzata degli utenti  | Consentire ai chiamanti di raggiungere un elenco personalizzato di utenti dell'organizzazione| Y | Y    |
| AA | Funzionalità del servizio | Trattamento after-hours and Holidays  |  | Y | Y    |
| AA | Funzionalità del servizio | Messaggio di saluto personalizzato utilizzando il testo per la sintesi vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione estensione   | Raggiungimento di un utente mediante composizione dell'estensione  | Y   | Y    |
| AA | Funzionalità del servizio | Cassetta postale per i chiamanti AA per lasciare un messaggio    |  | Y   | Y    |
| AA | Funzionalità del servizio | Più assegnazioni di numeri PSTN a un AA|  | Y | Y    |
| AA | Funzionalità tenant-admin | Amministrazione portale Web   |  | Y | N    |
| AA | Funzionalità tenant-admin | Cmdlet di PowerShell  |  | Y | Y    |
| Fax| Funzionalità del servizio | Integrazione fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Piano di testing suggerito e convalida dopo la migrazione per gli amministratori

Per convalidare la migrazione degli utenti alla segreteria telefonica cloud, lasciare una segreteria telefonica a un utente e controllare il corpo del messaggio in Outlook. I messaggi di segreteria telefonica cloud dispongono di un piè di pagina che legge:

"Grazie per l'utilizzo di trascrizione! Se non si vede una trascrizione in alto, è perché la qualità audio non è stata sufficientemente chiara per trascrivere ".

Quando si verifica la funzionalità della segreteria telefonica dopo la migrazione degli utenti, prendere in considerazione gli scenari seguenti:

- Convalidare l'accesso alla segreteria telefonica su tutti i tipi di endpoint nell'organizzazione, ad esempio app e telefoni IP.
- Convalidare con gli utenti di esempio che i messaggi di saluto personalizzati configurati vengono riprodotti ai chiamanti.
- Se l'organizzazione ha un requisito legale o di conformità per disabilitare la trascrizione per gli utenti, assicurarsi che sia disabilitata dopo la migrazione. Per ulteriori informazioni, vedere [set up cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Se sono stati precedentemente configurati i criteri e le regole della VM di Exchange, verificare che siano efficaci.
- Acquisire familiarità con i cmdlet di PowerShell per i servizi di segreteria cloud per modificare le impostazioni dell'utente.  

### <a name="user-experience-impact"></a>Impatto sull'esperienza utente

Di seguito è riportata una panoramica dell'esperienza di migrazione della segreteria telefonica per gli utenti finali.


|Funzionalità  |Modifica dell'esperienza utente|
|---------|---------|
|Notifica tramite posta elettronica | Nessuna modifica<br>Non viene inviato alcun messaggio di posta elettronica agli utenti che li notificano sull'attivazione/migrazione degli account vocali. |
|Accesso ai messaggi precedenti | Nessuna modifica<br>Gli utenti hanno accesso ai messaggi vocali precedenti in tutti gli endpoint supportati. |
|Ricezione di macchine virtuali in Outlook, app di questo| Nessuna modifica<br>Gli utenti continuano a ricevere i messaggi vocali in tutti gli endpoint supportati. |
|Trascrizione | Avanzato<br>La trascrizione di CVM ha un tasso di precisione molto più elevato e lingue supportate rispetto a ExchUMO. |
|Impostazione utente | Nuova esperienza<br>Gli utenti sono in grado di modificare le proprie preferenze da un portale di impostazioni utente (USP). Gli utenti possono accedere al proprio USP da un collegamento ipertestuale nella posta elettronica della segreteria telefonica oppure il pulsante Impostazioni utente nel proprio client di questo. https://aka.ms/vmsettings.
 |Funzionalità| Per informazioni dettagliate, vedere il confronto tra set di caratteristiche. |
|Regole di Outlook per i messaggi VM | Nessuna modifica<br>Le regole create in precedenza si applicheranno ai messaggi di CVM dopo la migrazione.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestione e provisioning degli utenti in CVM

I nuovi utenti di Skype for business verranno automaticamente provisionati per la segreteria telefonica cloud quando vengono creati. Per il provisioning di nuovi utenti di segreteria telefonica non è necessaria alcuna licenza o lavoro aggiuntivo. Per ulteriori informazioni sulla gestione dei criteri per gli utenti esistenti e nuovi, vedere [set up cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail) .

### <a name="admin-auto-attendant-management-experience"></a>Esperienza di gestione dell'operatore automatico di amministrazione

Per ulteriori informazioni sugli operatori automatici, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problemi noti

#### <a name="greeting-inconsistencies"></a>Incoerenze di saluto

L'accesso sottoscrittore potrebbe continuare a funzionare per il tenant finché il servizio non è completamente ritirato, anche dopo che tutti gli utenti sono stati migrati nella segreteria telefonica cloud. Per evitare confusione tra gli utenti e un'esperienza incoerente, disabilitare l'accesso sottoscrittore dopo la modifica del messaggio di saluto dopo la migrazione. A tale scopo, rimuovere il contatto EXUM per ogni riga di accesso del Sottoscrittore utilizzando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Trasferimento di chiamata dell'operatore automatico a PSTN

Per trasferire una chiamata di operatore automatico a un numero di telefono PSTN esterno tramite Skype for Business Server o un servizio di Response Group (RGS) su Skype for Business Server, creare un nuovo utente locale con inoltro di chiamata impostato sul numero di telefono PSTN o sul numero di telefono RGS. L'utente deve essere abilitato e configurato correttamente per VoIP aziendale e assegnato un criterio vocale.

#### <a name="shared-mailbox-is-still-accessible"></a>È ancora possibile accedere a una cassetta postale condivisa

Una cassetta postale condivisa configurata utilizzando la messaggistica unificata di Exchange Online continua a ricevere messaggi dopo la migrazione a CVM ed essere accessibile agli utenti tramite Outlook. Tuttavia, l'accesso alla modifica dei messaggi di saluto di queste cassette postali non sarà disponibile dopo la migrazione a CVM. I clienti con cassette postali condivise utilizzate per acquisire i chiamanti dell'operatore automatico devono sfruttare gli operatori automatici e le funzionalità delle cassette postali condivise delle code di chiamata, una volta rilasciate (ETA ottobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"Nome utente non utilizza Skype for business" Visualizza banner

Il servizio CVM si basa sull'infrastruttura di Microsoft teams e le chiamate da un client Skype for business potrebbero causare un banner informativo visualizzato sul client che recita: "nomeutente non utilizza Skype for business. Per un'esperienza più completa, passare a teams o avviare una riunione Skype.
Assicurarsi di aggiornare il client Skype for business degli utenti all'ultimo aggiornamento client di C2R per evitare che questo banner venga visualizzato.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurare il sistema di caselle vocali" porta a OWA

Fare clic su **Configura segreteria telefonica** dal client continuerà a prendere Skype for Business Server 2015/2013 clienti alla pagina del portale di Office Web Access (OWA) dopo la migrazione a CVM. Tutte le impostazioni sono state rimosse dalla scheda segreteria telefonica in OWA e un banner verrà visualizzato con un collegamento di reindirizzamento per consentire agli utenti di utilizzare il portale delle impostazioni utente di CVM.

#### <a name="changing-greeting-remotely"></a>Modifica del messaggio di saluto in remoto

L'accesso sottoscrittore PSTN non è supportato in CVM. Per gli utenti che hanno la necessità di modificare il proprio messaggio di saluto in remoto, è stata aggiunta un'opzione di menu "cambia il messaggio di saluto" alla segreteria telefonica IVR per i client mobili. Gli utenti possono chiamare questo servizio premendo e tenendo premuto il tasto "1" nel dial-pad del client per dispositivi mobili.
